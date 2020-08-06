---
title: Specificare eventi e colonne di dati per un file di traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- adding events
- traces [SQL Server], data columns
- deleting events
- removing events
- traces [SQL Server], events
ms.assetid: 7da715a3-2f03-4063-b6a4-20fd7b44e675
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb8639a187f1e7e091e382031886659bd47d7d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622972"
---
# <a name="specify-events-and-data-columns-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="c430c-102">Specificare eventi e colonne di dati per un file di traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c430c-102">Specify Events and Data Columns for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="c430c-103">In questo argomento viene descritto come specificare le classi degli eventi e le colonne di dati per le tracce utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c430c-103">This topic describes how to specify event classes and data columns for traces by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-specify-events-and-data-columns-for-a-trace"></a><span data-ttu-id="c430c-104">Per specificare eventi e colonne di dati per una traccia</span><span class="sxs-lookup"><span data-stu-id="c430c-104">To specify events and data columns for a trace</span></span>  
  
1.  <span data-ttu-id="c430c-105">Nella finestra di dialogo **Proprietà traccia** o **Proprietà modello di traccia** fare clic sulla scheda **Selezione eventi** .</span><span class="sxs-lookup"><span data-stu-id="c430c-105">On the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="c430c-106">La scheda **Selezione eventi** contiene un controllo griglia,</span><span class="sxs-lookup"><span data-stu-id="c430c-106">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="c430c-107">ovvero una tabella che include tutte le classi di evento tracciabili.</span><span class="sxs-lookup"><span data-stu-id="c430c-107">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="c430c-108">La tabella contiene una riga per ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="c430c-108">The table contains one row for each event class.</span></span> <span data-ttu-id="c430c-109">Le classi di evento possono differire leggermente a seconda del tipo e della versione del server cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="c430c-109">The event classes can differ slightly depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="c430c-110">Le classi di eventi sono identificate nella colonna **Eventi**della griglia e sono raggruppate per categoria di eventi.</span><span class="sxs-lookup"><span data-stu-id="c430c-110">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="c430c-111">Nelle altre colonne sono elencate le colonne di dati che possono essere restituite per ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="c430c-111">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="c430c-112">Nella scheda **Selezione eventi**usare il controllo griglia per aggiungere o rimuovere eventi e colonne di dati dal file di traccia.</span><span class="sxs-lookup"><span data-stu-id="c430c-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file.</span></span>  
  
3.  <span data-ttu-id="c430c-113">Per rimuovere eventi dalla traccia, deselezionare la casella di controllo nella colonna **Eventi** relativa a ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="c430c-113">To remove events from the trace, clear the check box in the **Events** column for each event class.</span></span>  
  
4.  <span data-ttu-id="c430c-114">Per includere eventi in una traccia, selezionare la casella nella colonna **Eventi** per ogni classe di evento oppure selezionare una colonna di dati corrispondente a un evento.</span><span class="sxs-lookup"><span data-stu-id="c430c-114">To include events in a trace, check the box in the **Events** column for each event class, or check a data column that corresponds to an event.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c430c-115">Se la traccia verrà correlata ai dati di Monitoraggio di sistema o di Performance Monitor, è necessario includere nella traccia le colonne di dati **Ora di inizio** e **Ora di fine** .</span><span class="sxs-lookup"><span data-stu-id="c430c-115">If the trace is going be correlated with System Monitor or Performance Monitor data, both **Start Time** and **End Time** data columns must be included in the trace.</span></span>  
  
 <span data-ttu-id="c430c-116">Quando si include una classe di evento, nella traccia vengono inserite tutte le colonne di dati associate se è stata selezionata la casella corrispondente a un evento.</span><span class="sxs-lookup"><span data-stu-id="c430c-116">When you include an event class, every associated data column is also included to the trace, if you have checked the box corresponding to an event.</span></span> <span data-ttu-id="c430c-117">Se è stata selezionata la casella per una colonna specifica, nella traccia verrà inclusa solo tale colonna.</span><span class="sxs-lookup"><span data-stu-id="c430c-117">If you checked the box for a particular column, only that column is included in the trace.</span></span>  
  
1.  <span data-ttu-id="c430c-118">Per rimuovere colonne di dati da una classe di evento, deselezionare le caselle di controllo della colonna di dati nella riga della classe oppure fare clic con il pulsante destro del mouse sull'intestazione della colonna e selezionare l'opzione **Deseleziona colonna** .</span><span class="sxs-lookup"><span data-stu-id="c430c-118">To remove data columns from an event class, clear the check boxes from the data column in the event class row, or right-click on the column header and select the **Deselect column** option.</span></span>  
  
2.  <span data-ttu-id="c430c-119">Applicare facoltativamente filtri alla traccia.</span><span class="sxs-lookup"><span data-stu-id="c430c-119">Optionally, apply filters to the trace.</span></span> <span data-ttu-id="c430c-120">Per altre informazioni, vedere [Filtrare eventi in una traccia &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="c430c-120">For more information, see [Filter Events in a Trace &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c430c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c430c-121">See Also</span></span>  
 [<span data-ttu-id="c430c-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c430c-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
