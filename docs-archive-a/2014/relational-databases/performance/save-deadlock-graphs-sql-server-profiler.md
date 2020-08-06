---
title: Salvare eventi Deadlock Graph (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], saving deadlock graphs
- graphs [SQL Server]
- saving deadlock graphs
ms.assetid: bf1fc906-abd6-4a89-842e-da0d66b2defe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cdd0bd808ba4b934e5b2d91c9079909acf6e3997
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634985"
---
# <a name="save-deadlock-graphs-sql-server-profiler"></a><span data-ttu-id="1c562-102">Salvare eventi Deadlock Graph (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="1c562-102">Save Deadlock Graphs (SQL Server Profiler)</span></span>
  <span data-ttu-id="1c562-103">In questo argomento viene descritto come salvare un evento Deadlock Graph utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c562-103">This topic describes how to save a deadlock graph by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="1c562-104">Gli eventi Deadlock Graph vengono salvati come file XML.</span><span class="sxs-lookup"><span data-stu-id="1c562-104">Deadlock graphs are saved as XML files.</span></span>  
  
### <a name="to-save-deadlock-graph-events-separately"></a><span data-ttu-id="1c562-105">Per salvare gli eventi Deadlock Graph separatamente</span><span class="sxs-lookup"><span data-stu-id="1c562-105">To save deadlock graph events separately</span></span>  
  
1.  <span data-ttu-id="1c562-106">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c562-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="1c562-107">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="1c562-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c562-108">Se l'opzione **Avvia traccia non appena viene stabilita una connessione** è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="1c562-108">If **Start tracing immediately after making connection** is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="1c562-109">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="1c562-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="1c562-110">Nella finestra di dialogo Proprietà traccia digitare un nome per la traccia nella casella**Nome traccia** .</span><span class="sxs-lookup"><span data-stu-id="1c562-110">In the Trace Properties dialog box, type a name for the trace in the**Trace name** box.</span></span>  
  
3.  <span data-ttu-id="1c562-111">Nell'elenco **Modello** selezionare un modello di traccia sul quale basare la traccia oppure selezionare **Vuoto** per non utilizzare alcun modello.</span><span class="sxs-lookup"><span data-stu-id="1c562-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="1c562-112">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c562-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="1c562-113">Selezionare la casella di controllo**Salva nel file** per acquisire la traccia in un file.</span><span class="sxs-lookup"><span data-stu-id="1c562-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="1c562-114">Specificare un valore per l'opzione **Dimensioni massime del file**.</span><span class="sxs-lookup"><span data-stu-id="1c562-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="1c562-115">Facoltativamente selezionare le caselle di controllo **Consenti rollover dei file** e **Dati di traccia elaborati dal server**.</span><span class="sxs-lookup"><span data-stu-id="1c562-115">Optionally, select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="1c562-116">Selezionare la casella di controllo **Salva nella tabella** per acquisire la traccia in una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="1c562-116">Select the **Save to table** check box to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="1c562-117">Facoltativamente fare clic su **Numero massimo di righe**e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="1c562-117">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="1c562-118">Facoltativamente, selezionare la casella di controllo **Data e ora di arresto della traccia** e specificare una data e un'ora di arresto della traccia.</span><span class="sxs-lookup"><span data-stu-id="1c562-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="1c562-119">Fare clic sulla scheda **Selezione eventi**.</span><span class="sxs-lookup"><span data-stu-id="1c562-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="1c562-120">Nella colonna di dati **Eventi**espandere la categoria di eventi **Locks**e quindi selezionare la casella di controllo **Deadlock graph**.</span><span class="sxs-lookup"><span data-stu-id="1c562-120">In the **Events**data column, expand the **Locks**event category, and then select the **Deadlock graph**check box.</span></span> <span data-ttu-id="1c562-121">Se la categoria di eventi Locks non è disponibile, selezionare **Mostra tutti gli eventi** per visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="1c562-121">If the Locks event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="1c562-122">Verrà visualizzata la finestra di dialogo **Impostazioni estrazione event**viene aggiunta alla finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="1c562-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="1c562-123">Nella scheda **Impostazioni estrazione eventi**fare clic su **Salva eventi deadlock XML separatamente**.</span><span class="sxs-lookup"><span data-stu-id="1c562-123">On the **Events Extraction Settings**tab, click **Save Deadlock XML Events Separately**.</span></span>  
  
9. <span data-ttu-id="1c562-124">Nella finestra di dialogo **Salva con nome** digitare il nome del file nel quale memorizzare gli eventi Deadlock Graph.</span><span class="sxs-lookup"><span data-stu-id="1c562-124">In the **Save As** dialog box, enter the name of the file in which to store the deadlock graph events.</span></span>  
  
10. <span data-ttu-id="1c562-125">Fare clic su **Tutti i batch deadlock XML in un singolo file** per salvare tutti gli eventi Deadlock Graph in un file XML singolo oppure fare clic su **Crea un file distinto per ogni singolo batch deadlock XML**per creare un nuovo file XML per ogni evento Deadlock Graph.</span><span class="sxs-lookup"><span data-stu-id="1c562-125">Click **All Deadlock XML batches in a single file** to save all deadlock graph events in a single XML file, or click **Each Deadlock XML batch in a distinct file**to create a new XML file for each deadlock graph.</span></span>  
  
 <span data-ttu-id="1c562-126">Dopo aver salvato il file deadlock, è possibile aprire il file in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c562-126">After you have saved the deadlock file, you can open the file in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1c562-127">Per ulteriori informazioni, vedere [aprire, visualizzare e stampare un file Deadlock &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="1c562-127">For more information, see [Open, View, and Print a Deadlock File &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c562-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c562-128">See Also</span></span>  
 [<span data-ttu-id="1c562-129">Analizzare deadlock con SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1c562-129">Analyze Deadlocks with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler.md)  
  
  
