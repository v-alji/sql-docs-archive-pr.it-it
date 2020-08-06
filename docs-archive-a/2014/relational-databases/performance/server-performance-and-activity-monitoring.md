---
title: Monitoraggio delle prestazioni e dell'attività del server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- activity monitoring [SQL Server]
- traces [SQL Server], how-to topics
- monitoring server performance [SQL Server], activity monitoring
- stored procedures [SQL Server], traces
- performance [SQL Server], servers
- servers [SQL Server], performance
- SQL Server Profiler, how-to topics
- SQL Server Management Studio [SQL Server], monitoring system
- Profiler [SQL Server Profiler], how-to topics
ms.assetid: f9abe48d-d6e9-4c38-a355-fc5eb5a95a25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0fa7902d68c587a7733f07ceb8daccd3a6a98fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637817"
---
# <a name="server-performance-and-activity-monitoring"></a><span data-ttu-id="52131-102">Monitoraggio delle prestazioni e dell'attività del server</span><span class="sxs-lookup"><span data-stu-id="52131-102">Server Performance and Activity Monitoring</span></span>
  <span data-ttu-id="52131-103">L'obiettivo del monitoraggio dei database consiste nella valutazione delle prestazioni di un server.</span><span class="sxs-lookup"><span data-stu-id="52131-103">The goal of monitoring databases is to assess how a server is performing.</span></span> <span data-ttu-id="52131-104">Un monitoraggio efficace implica l'esecuzione di snapshot periodici delle prestazioni correnti al fine di isolare i processi che causano problemi, nonché la raccolta continua di dati nel tempo per tenere traccia delle tendenze delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="52131-104">Effective monitoring involves taking periodic snapshots of current performance to isolate processes that are causing problems, and gathering data continuously over time to track performance trends.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="52131-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il sistema operativo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows offrono utilità che consentono di visualizzare la condizione corrente del database e di tenere traccia delle prestazioni in caso di variazioni.</span><span class="sxs-lookup"><span data-stu-id="52131-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows operating system provide utilities that let you view the current condition of the database and to track performance as conditions change.</span></span>  
  
 <span data-ttu-id="52131-106">Nella sezione seguente sono contenuti argomenti che descrivono l'utilizzo degli strumenti di monitoraggio delle prestazioni e dell'attività disponibili in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e in Windows.</span><span class="sxs-lookup"><span data-stu-id="52131-106">The following section contains topics that describe how to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows performance and activity monitoring tools.</span></span> <span data-ttu-id="52131-107">Questa lezione contiene i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="52131-107">It contains the following topics:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52131-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="52131-108">In This Section</span></span>  
 <span data-ttu-id="52131-109">**Per eseguire attività di monitoraggio con gli strumenti di Windows**</span><span class="sxs-lookup"><span data-stu-id="52131-109">**To perform monitoring tasks with Windows tools**</span></span>  
  
-   [<span data-ttu-id="52131-110">Avviare il Monitoraggio di sistema &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-110">Start System Monitor &#40;Windows&#41;</span></span>](start-system-monitor-windows.md)  
  
-   [<span data-ttu-id="52131-111">Visualizzazione del log applicazioni di &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-111">View the Windows Application Log &#40;Windows&#41;</span></span>](view-the-windows-application-log-windows-10.md)  
  
 <span data-ttu-id="52131-112">**Per creare avvisi del database di SQL Server con gli strumenti di Windows**</span><span class="sxs-lookup"><span data-stu-id="52131-112">**To create SQL Server database alerts with Windows tools**</span></span>  
  
-   [<span data-ttu-id="52131-113">Impostazione di un avviso del database di SQL Server &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-113">Set Up a SQL Server Database Alert &#40;Windows&#41;</span></span>](set-up-a-sql-server-database-alert-windows.md)  
  
 <span data-ttu-id="52131-114">**Per eseguire attività di monitoraggio con SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="52131-114">**To perform monitoring tasks with SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="52131-115">Visualizzazione del log degli errori di SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-115">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="52131-116">Aprire Monitoraggio attività &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-116">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)  
  
 <span data-ttu-id="52131-117">**Per eseguire attività di monitoraggio con Traccia SQL utilizzando stored procedure Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="52131-117">**To perform monitoring tasks with SQL Trace by using Transact-SQL stored procedures**</span></span>  
  
-   [<span data-ttu-id="52131-118">Creare una traccia &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-118">Create a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
-   [<span data-ttu-id="52131-119">Impostare un filtro di traccia &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-119">Set a Trace Filter &#40;Transact-SQL&#41;</span></span>](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md)  
  
-   [<span data-ttu-id="52131-120">Modificare una traccia esistente &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-120">Modify an Existing Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/modify-an-existing-trace-transact-sql.md)  
  
-   [<span data-ttu-id="52131-121">Visualizzare una traccia salvata &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-121">View a Saved Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-a-saved-trace-transact-sql.md)  
  
-   [<span data-ttu-id="52131-122">Visualizzare informazioni sui filtri &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-122">View Filter Information &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-filter-information-transact-sql.md)  
  
-   [<span data-ttu-id="52131-123">Eliminare una traccia &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-123">Delete a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/delete-a-trace-transact-sql.md)  
  
 <span data-ttu-id="52131-124">**Per creare e modificare le tracce tramite SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="52131-124">**To create and modify traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="52131-125">Creare una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-125">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-126">Impostare opzioni di traccia globali &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-126">Set Global Trace Options &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-127">Specificare eventi e colonne di dati per un file di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-127">Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-128">Creare uno script Transact-SQL per l'esecuzione di una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-128">Create a Transact-SQL Script for Running a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-transact-sql-script-for-running-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-129">Salvare i risultati della traccia in un file &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-129">Save Trace Results to a File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-130">Impostare le dimensioni massime di un file di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-130">Set a Maximum File Size for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-file-size-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-131">Salvare i risultati della traccia in una tabella &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-131">Save Trace Results to a Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-132">Impostare le dimensioni massime di un file di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-132">Set a Maximum Table Size for a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-table-size-for-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-133">Filtrare eventi in una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-133">Filter Events in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-134">Visualizzare informazioni sui filtri &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-134">View Filter Information &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-135">Modificare un filtro &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-135">Modify a Filter &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-136">Filtrare gli eventi in base all'ora di inizio &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-136">Filter Events Based on the Event Start Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-start-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-137">Filtrare gli eventi in base all'ora di fine &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-137">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-138">Filtrare gli ID del processo server &#40;SPIDs&#41; in una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-138">Filter Server Process IDs &#40;SPIDs&#41; in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-server-process-ids-spids-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-139">Organizzare le colonne visualizzate in una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-139">Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="52131-140">**Per avviare, sospendere e arrestare le tracce tramite SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="52131-140">**To start, pause, and stop traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="52131-141">Avviare una traccia automaticamente dopo la connessione a un server &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-141">Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-142">Sospendere una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-142">Pause a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-143">Arrestare in pausa una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-143">Stop a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-144">Eseguire una traccia dopo la sospensione o l'arresto &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-144">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
 <span data-ttu-id="52131-145">**Per aprire le tracce e configurare la relativa modalità di visualizzazione tramite SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="52131-145">**To open traces and configure how traces are displayed by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="52131-146">Aprire un file di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-146">Open a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-147">Aprire una tabella di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-147">Open a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-148">Cancellare il contenuto di una finestra di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-148">Clear a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-149">Chiudere una finestra di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-149">Close a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/close-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-150">Impostare i valori predefiniti per una definizione di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-150">Set Trace Definition Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-definition-defaults-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-151">Impostare i valori predefiniti per la visualizzazione di una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-151">Set Trace Display Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="52131-152">**Per riprodurre le tracce tramite SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="52131-152">**To replay traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="52131-153">Riprodurre un file di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-153">Replay a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-154">Riprodurre una tabella di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-154">Replay a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-155">Riprodurre un solo evento alla volta &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-155">Replay a Single Event at a Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-single-event-at-a-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-156">Riprodurre fino a un punto di interruzione &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-156">Replay to a Breakpoint &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-breakpoint-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-157">Riprodurre fino a un cursore &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-157">Replay to a Cursor &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-158">Riprodurre uno script Transact-SQL &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-158">Replay a Transact-SQL Script &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-transact-sql-script-sql-server-profiler.md)  
  
 <span data-ttu-id="52131-159">**Per creare, modificare e utilizzare modelli di traccia tramite SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="52131-159">**To create, modify, and use trace templates by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="52131-160">Creare un modello di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-160">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-161">Modificare un modello di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-161">Modify a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-162">Ottenere un modello da una traccia in esecuzione &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-162">Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-163">Derivare un modello da un file di traccia o da una tabella di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-163">Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-164">Esportare un modello di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-164">Export a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/export-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-165">Esportare un modello di traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-165">Import a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/import-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="52131-166">**Per raccogliere e monitorare le prestazioni del server tramite le tracce di SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="52131-166">**To use SQL Server Profiler traces to collect and monitor server performance**</span></span>  
  
-   [<span data-ttu-id="52131-167">Trovare un valore o una colonna di dati durante l'esecuzione di una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-167">Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-168">Salvare eventi Deadlock Graph &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-168">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-169">Salvataggio di eventi Showplan XML in modo indipendente &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-169">Save Showplan XML Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-170">Salvataggio della classe di eventi Showplan XML Statistics Profile Events in file distinti &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-170">Save Showplan XML Statistics Profile Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-statistics-profile-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-171">Estrarre uno script da una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-171">Extract a Script from a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/extract-a-script-from-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="52131-172">Correlare una traccia e i dati dei registri di prestazioni di Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="52131-172">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
