---
title: Salvare la classe di eventi Showplan XML Statistics Profile Events in file distinti (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan XML events
- saving Showplan XML events
- events [SQL Server], Showplan XML
ms.assetid: df393f13-d538-4d94-8155-9c2fdf5f755d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: be0c02f8396df81af803c365b9ede42610353ed3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716287"
---
# <a name="save-showplan-xml-statistics-profile-events-separately-sql-server-profiler"></a><span data-ttu-id="d3b5b-102">Salvataggio della classe di eventi Showplan XML Statistics Profile Events in file distinti (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="d3b5b-102">Save Showplan XML Statistics Profile Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="d3b5b-103">Questo argomento descrive la procedura da seguire per salvare gli eventi **Showplan XML Statistics Profile** acquisiti in tracce in file SQLPlan distinti tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3b5b-103">This topic describes how to save **Showplan XML Statistics Profile** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="d3b5b-104">È possibile aprire i file di eventi **Showplan XML Statistics Profile** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]per visualizzare graficamente il piano di esecuzione di ogni evento.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-104">You can open the **Showplan XML Statistics Profile** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-statistics-events-separately"></a><span data-ttu-id="d3b5b-105">Per salvare eventi Showplan XML Statistics Profile in file distinti</span><span class="sxs-lookup"><span data-stu-id="d3b5b-105">To save Showplan XML statistics events separately</span></span>  
  
1.  <span data-ttu-id="d3b5b-106">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3b5b-106">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="d3b5b-107">Verrà visualizzata la finestra di dialogo **Proprietà traccia** .</span><span class="sxs-lookup"><span data-stu-id="d3b5b-107">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d3b5b-108">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box does not appear and the trace begins instead.</span></span> <span data-ttu-id="d3b5b-109">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="d3b5b-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="d3b5b-110">Nella finestra di dialogo **Proprietà traccia** digitare un nome per la traccia nella casella **Nome traccia** .</span><span class="sxs-lookup"><span data-stu-id="d3b5b-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="d3b5b-111">Nell'elenco **Modello** selezionare un modello di traccia su cui basare la traccia oppure selezionare **Vuoto** se non si desidera utilizzare alcun modello.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-111">In the **Use the template** list, select a trace template to base the trace on, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="d3b5b-112">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3b5b-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="d3b5b-113">Fare clic su**Salva nel file**per acquisire la traccia in un file.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-113">Click**Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="d3b5b-114">Specificare un valore per l'opzione **Dimensioni massime del file**.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="d3b5b-115">Facoltativamente, selezionare **Abilita rollover dei file** e **dati di traccia dei processi server**.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-115">Optionally select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="d3b5b-116">Fare clic su**Salva nella tabella** per acquisire la traccia in una tabella del database.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-116">Click**Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="d3b5b-117">Facoltativamente, fare clic su **Imposta numero massimo di righe**e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="d3b5b-118">Facoltativamente, selezionare la casella di controllo **Abilita ora di arresto della traccia** e specificare una data e un'ora di arresto.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-118">Optionally select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="d3b5b-119">Fare clic sulla scheda **Selezione eventi**.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="d3b5b-120">Nella colonna di dati **Events**espandere la categoria di eventi **Performance**e quindi selezionare la casella di controllo **Showplan XML Statistics Profile**.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML Statistics Profile**check box.</span></span> <span data-ttu-id="d3b5b-121">Se la categoria di eventi **Performance** non è visualizzata, selezionare la casella di controllo **Mostra tutti gli eventi** .</span><span class="sxs-lookup"><span data-stu-id="d3b5b-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="d3b5b-122">La scheda **Impostazioni estrazione eventi**viene aggiunta alla finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog.</span></span>  
  
8.  <span data-ttu-id="d3b5b-123">Scegliere **Impostazioni estrazione event**selezionare la casella di controllo **Salva eventi Showplan XML separatamente**.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="d3b5b-124">Nella finestra di dialogo **Salva con nome** immettere un nome per il file in cui archiviare gli eventi **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="d3b5b-124">In the **Save As** dialog box, enter the file name to store the **Showplan XML Statistics Profile** events.</span></span>  
  
10. <span data-ttu-id="d3b5b-125">Fare clic su **Tutti i batch in un singolo file** per salvare tutti gli eventi **Showplan XML Statistics Profile** in un unico file XML oppure fare clic su **Crea un file distinto per ogni singolo batch Showplan XML**per creare un nuovo file XML per ogni evento **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="d3b5b-125">Click **All batches in a single file** to save all **Showplan XML Statistics Profile** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML Statistics Profile** event.</span></span>  
  
11. <span data-ttu-id="d3b5b-126">Per visualizzare il file di eventi **Showplan XML Statistics Profile** in SQL Server Management Studio, scegliere **Apri** dal menu **File**e quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-126">To view the **Showplan XML Statistics Profile** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="d3b5b-127">Spostarsi sulla directory in cui è stato salvato il file o i file di eventi **Showplan XML Statistics Profile** , selezionare il file desiderato e quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-127">Navigate to the directory where you saved the **Showplan XML Statistics Profile** event file or files to select one and open it.</span></span> <span data-ttu-id="d3b5b-128">I file di eventi**Showplan XML Statistics Profile** sono contraddistinti dall'estensione SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="d3b5b-128">**Showplan XML Statistics Profile** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b5b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3b5b-129">See Also</span></span>  
 [<span data-ttu-id="d3b5b-130">Analizzare query con risultati SHOWPLAN in SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d3b5b-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
