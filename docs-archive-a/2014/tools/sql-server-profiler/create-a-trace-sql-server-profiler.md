---
title: Creare una traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], creating
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7d73333bbf0ba985ed4952e03584b4e4c130ab6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711276"
---
# <a name="create-a-trace-sql-server-profiler"></a><span data-ttu-id="75bf4-102">Creare una traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="75bf4-102">Create a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="75bf4-103">In questo argomento viene descritto come utilizzare [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per creare una traccia.</span><span class="sxs-lookup"><span data-stu-id="75bf4-103">This topic describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="75bf4-104">Per creare una traccia</span><span class="sxs-lookup"><span data-stu-id="75bf4-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="75bf4-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75bf4-105">On the **File** menu, click **New Trace**, and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="75bf4-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia** .</span><span class="sxs-lookup"><span data-stu-id="75bf4-106">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75bf4-107">Se la casella di controllo **Avvia traccia non appena viene stabilita una connessione** è selezionata, la finestra di dialogo **Proprietà traccia** non verrà visualizzata e verrà invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="75bf4-107">The **Trace Properties** dialog box fails to appear, and the trace begins instead, if **Start tracing immediately after making connection** is selected.</span></span> <span data-ttu-id="75bf4-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="75bf4-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="75bf4-109">Nella casella **Nome traccia** digitare un nome per la traccia.</span><span class="sxs-lookup"><span data-stu-id="75bf4-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="75bf4-110">Nell'elenco **Modello** selezionare un modello di traccia sul quale basare la traccia oppure selezionare **Vuoto** per non utilizzare alcun modello.</span><span class="sxs-lookup"><span data-stu-id="75bf4-110">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="75bf4-111">Per salvare i risultati della traccia, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="75bf4-111">To save the trace results, do one of the following:</span></span>  
  
    -   <span data-ttu-id="75bf4-112">Fare clic su **Salva nel file** per acquisire la traccia in un file.</span><span class="sxs-lookup"><span data-stu-id="75bf4-112">Click **Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="75bf4-113">Specificare un valore per l'opzione **Dimensioni massime del file**.</span><span class="sxs-lookup"><span data-stu-id="75bf4-113">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="75bf4-114">Il valore predefinito è 5 megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="75bf4-114">The default value is 5 megabytes (MB).</span></span>  
  
         <span data-ttu-id="75bf4-115">Facoltativamente, selezionare **Consenti rollover dei file** per creare automaticamente nuovi file quando viene raggiunta la dimensione massima consentita per i file.</span><span class="sxs-lookup"><span data-stu-id="75bf4-115">Optionally, select **Enable file rollover** to automatically create new files when the maximum file size is reached.</span></span> <span data-ttu-id="75bf4-116">È anche possibile selezionare facoltativamente **Dati di traccia elaborati dal server**per assegnare l'elaborazione dei dati di traccia al servizio che esegue la traccia, invece che all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="75bf4-116">You can also optionally select **Server processes trace data**, which causes the service that is running the trace to process trace data instead of the client application.</span></span> <span data-ttu-id="75bf4-117">Quando i dati di traccia vengono elaborati dal server, in condizioni di sovraccarico non verrà ignorato alcun evento, ma è possibile che si verifichi un peggioramento delle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="75bf4-117">When the server processes trace data, no events are skipped even under stress conditions, but server performance may be affected.</span></span>  
  
    -   <span data-ttu-id="75bf4-118">Fare clic su **Salva nella tabella** per acquisire la traccia in una tabella del database.</span><span class="sxs-lookup"><span data-stu-id="75bf4-118">Click **Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="75bf4-119">Facoltativamente fare clic su **Numero massimo di righe**e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="75bf4-119">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="75bf4-120">Se i risultati della traccia non vengono salvati in un file o in una tabella, è possibile visualizzare la traccia quando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] è aperto.</span><span class="sxs-lookup"><span data-stu-id="75bf4-120">When you do not save the trace results to a file or table, you can view the trace while [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is open.</span></span> <span data-ttu-id="75bf4-121">I risultati della traccia andranno tuttavia persi dopo l'arresto della traccia e la chiusura di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75bf4-121">However, you lose the trace results after you stop the trace and close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="75bf4-122">Per evitare tale perdita dei risultati della traccia, scegliere **Salva** dal menu **File** per salvare i risultati prima di chiudere [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75bf4-122">To avoid losing the trace results in this way, click **Save** on the **File** menu to save the results before you close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
5.  <span data-ttu-id="75bf4-123">Facoltativamente, selezionare la casella di controllo **Data e ora di arresto della traccia** e specificare una data e un'ora di arresto della traccia.</span><span class="sxs-lookup"><span data-stu-id="75bf4-123">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="75bf4-124">Per aggiungere o rimuovere eventi, colonne di dati o filtri, fare clic sulla scheda **Selezione eventi**.</span><span class="sxs-lookup"><span data-stu-id="75bf4-124">To add or remove events, data columns or filters, click the **Events Selection**tab.</span></span> <span data-ttu-id="75bf4-125">Per altre informazioni, vedere [Specificare eventi e colonne di dati per un file di traccia &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="75bf4-125">For more information, see: [Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span></span>  
  
7.  <span data-ttu-id="75bf4-126">Fare clic su **Esegui** per avviare la traccia.</span><span class="sxs-lookup"><span data-stu-id="75bf4-126">Click **Run** to start the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bf4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75bf4-127">See Also</span></span>  
 <span data-ttu-id="75bf4-128">[Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="75bf4-128">[Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="75bf4-129">[Modelli e autorizzazioni di SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="75bf4-129">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 <span data-ttu-id="75bf4-130">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="75bf4-130">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="75bf4-131">Correlare una traccia e i dati dei registri di prestazioni di Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="75bf4-131">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
