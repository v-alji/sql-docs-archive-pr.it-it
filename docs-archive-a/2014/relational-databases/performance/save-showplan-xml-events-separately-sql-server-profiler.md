---
title: Salvare eventi Showplan XML in modo indipendente (SQL Server Profiler) | Microsoft Docs
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
ms.assetid: 33320a7a-36e8-401c-876d-5b82c49abd85
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 240fb408bb3ed8585ecc915ba4829ac21285d241
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637248"
---
# <a name="save-showplan-xml-events-separately-sql-server-profiler"></a><span data-ttu-id="fe3f7-102">Salvataggio di eventi Showplan XML in modo indipendente (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fe3f7-102">Save Showplan XML Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="fe3f7-103">In questo argomento viene illustrato come salvare eventi **Showplan XML** acquisiti in tracce in file SQLPlan distinti utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe3f7-103">This topic describes how to save **Showplan XML** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="fe3f7-104">È possibile aprire i file degli eventi **Showplan XML** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]per visualizzare il piano di esecuzione grafico per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-104">You can open the **Showplan XML** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-events-separately"></a><span data-ttu-id="fe3f7-105">Per salvare gli eventi Showplan XML in modo indipendente</span><span class="sxs-lookup"><span data-stu-id="fe3f7-105">To save Showplan XML events separately</span></span>  
  
1.  <span data-ttu-id="fe3f7-106">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="fe3f7-107">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fe3f7-108">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="fe3f7-109">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="fe3f7-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="fe3f7-110">Nella finestra di dialogo **Proprietà traccia** digitare un nome per la traccia nella casella **Nome traccia** .</span><span class="sxs-lookup"><span data-stu-id="fe3f7-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="fe3f7-111">Nell'elenco **Modello** selezionare un modello di traccia sul quale basare la traccia oppure selezionare **Vuoto** per non utilizzare alcun modello.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="fe3f7-112">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe3f7-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="fe3f7-113">Selezionare la casella di controllo**Salva nel file** per acquisire la traccia in un file.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="fe3f7-114">Specificare un valore per l'opzione **Dimensioni massime del file**.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-114">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="fe3f7-115">Se lo si desidera, selezionare le caselle di controllo **Consenti rollover dei file** e **Dati di traccia elaborati dal server** .</span><span class="sxs-lookup"><span data-stu-id="fe3f7-115">Optionally, select the **Enable file rollover** and **Server processes trace data** check boxes.</span></span>  
  
    -   <span data-ttu-id="fe3f7-116">Selezionare la casella di controllo**Salva nella tabella** per acquisire la traccia in una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-116">Select the**Save to table** check box to capture the trace to a database table.</span></span> <span data-ttu-id="fe3f7-117">Facoltativamente, fare clic su **Imposta numero massimo di righe**e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="fe3f7-118">Facoltativamente, selezionare la casella di controllo **Data e ora di arresto della traccia** e specificare una data e un'ora di arresto della traccia.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="fe3f7-119">Fare clic sulla scheda **Selezione eventi**.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="fe3f7-120">Nella finestra di dialogo **Eventi**espandere la categoria di eventi **Prestazioni**e quindi selezionare la casella di controllo **Showplan XML**.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML**check box.</span></span> <span data-ttu-id="fe3f7-121">Se la categoria di eventi **Performance** non è visualizzata, selezionare la casella di controllo **Mostra tutti gli eventi** .</span><span class="sxs-lookup"><span data-stu-id="fe3f7-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="fe3f7-122">Verrà visualizzata la finestra di dialogo **Impostazioni estrazione event**viene aggiunta alla finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="fe3f7-123">Scegliere **Impostazioni estrazione event**selezionare la casella di controllo **Salva eventi Showplan XML separatamente**.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="fe3f7-124">Nella finestra di dialogo **Salva con nome** immettere il nome del file in cui archiviare gli eventi **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="fe3f7-124">In the **Save As** dialog box, enter the name of the file in which to store the **Showplan XML** events.</span></span>  
  
10. <span data-ttu-id="fe3f7-125">Fare clic su **Tutti i batch Showplan XML in un singolo file** per salvare tutti gli eventi **Showplan XML** in un unico file XML oppure su **Crea un file distinto per ogni singolo batch Showplan XML**per creare un nuovo file XML per ogni evento **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="fe3f7-125">Click **All XML Showplan batches in a single file** to save all **Showplan XML** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML** event.</span></span>  
  
11. <span data-ttu-id="fe3f7-126">Per visualizzare i file degli eventi **Showplan XML** in SQL Server Management Studio, scegliere **Apri** dal menu **File**e quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-126">To view the **Showplan XML** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="fe3f7-127">Passare alla directory in cui sono stati salvati i file o il file degli eventi **Showplan XML** per selezionarne uno e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-127">Navigate to the directory where you saved the **Showplan XML** event file or files to select one and open it.</span></span> <span data-ttu-id="fe3f7-128">I file degli eventi**Showplan XML** hanno estensione SqlPlan.</span><span class="sxs-lookup"><span data-stu-id="fe3f7-128">**Showplan XML** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe3f7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe3f7-129">See Also</span></span>  
 [<span data-ttu-id="fe3f7-130">Analizzare query con risultati SHOWPLAN in SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fe3f7-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
