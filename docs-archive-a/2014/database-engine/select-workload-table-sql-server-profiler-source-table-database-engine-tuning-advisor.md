---
title: Tabella di origine SQL Server Profiler-Ottimizzazione guidata motore di database-selezionare la tabella del carico di lavoro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.sourcetable.f1
helpviewer_keywords:
- Select Workload Table dialog box
- Source Table dialog box
ms.assetid: 51185be7-7092-480a-a52c-cf7786c4a0a0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d10899c01df8e7fbc7ee45d108841a18d3248500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627372"
---
# <a name="sql-server-profiler---source-table-database-engine-tuning-advisor---select-workload-table"></a><span data-ttu-id="46dca-102">Tabella di origine SQL Server Profiler-Ottimizzazione guidata motore di database-selezionare la tabella del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="46dca-102">SQL Server Profiler - Source Table-Database Engine Tuning Advisor - Select Workload Table</span></span>
  <span data-ttu-id="46dca-103">Questa finestra di dialogo viene usata in Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] e in Ottimizzazione guidata [!INCLUDE[ssDE](../includes/ssde-md.md)] per selezionare tabelle.</span><span class="sxs-lookup"><span data-stu-id="46dca-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] and [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor use this dialog box to select tables.</span></span>  
  
 <span data-ttu-id="46dca-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], usare la finestra di dialogo **Tabella di origine** per specificare una tabella di origine per una tabella di traccia.</span><span class="sxs-lookup"><span data-stu-id="46dca-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use the **Source Table** dialog box to specify a source table for a trace table.</span></span> <span data-ttu-id="46dca-105">Si tratta di una tabella dalla quale viene caricata una traccia e il cui contenuto viene visualizzato o utilizzato per riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="46dca-105">This is a table from which a trace is loaded, and the contents of which are viewed or used for replaying the trace.</span></span>  
  
 <span data-ttu-id="46dca-106">In Ottimizzazione guidata [!INCLUDE[ssDE](../includes/ssde-md.md)], usare la finestra di dialogo **Seleziona tabella carico di lavoro** per selezionare una tabella di database contenente informazioni di traccia di [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] da usare come carico di lavoro per l'ottimizzazione o per visualizzare un'anteprima del contenuto della tabella prima di avviare l'analisi per l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="46dca-106">In [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor, use the **Select Workload Table** dialog box to select a database table that contains [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace information to use as a tuning workload, or to preview the table contents before starting tuning analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="46dca-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="46dca-107">Options</span></span>  
 <span data-ttu-id="46dca-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="46dca-108">**SQL Server**</span></span>  
 <span data-ttu-id="46dca-109">Indica l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a cui si è attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="46dca-109">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] currently connected.</span></span> <span data-ttu-id="46dca-110">Questo campo viene popolato automaticamente e non è possibile aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="46dca-110">This field is populated automatically and cannot be updated.</span></span>  
  
 <span data-ttu-id="46dca-111">**Database**</span><span class="sxs-lookup"><span data-stu-id="46dca-111">**Database**</span></span>  
 <span data-ttu-id="46dca-112">Consente di specificare il database che include la tabella di traccia.</span><span class="sxs-lookup"><span data-stu-id="46dca-112">Specify the database where the trace table is located.</span></span>  
  
 <span data-ttu-id="46dca-113">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="46dca-113">**Owner**</span></span>  
 <span data-ttu-id="46dca-114">Indica il proprietario della tabella di traccia.</span><span class="sxs-lookup"><span data-stu-id="46dca-114">Specifies the owner of the trace table.</span></span> <span data-ttu-id="46dca-115">Questo campo viene popolato automaticamente con il valore **dbo**.</span><span class="sxs-lookup"><span data-stu-id="46dca-115">This field is populated automatically as **dbo**.</span></span>  
  
 <span data-ttu-id="46dca-116">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="46dca-116">**Table**</span></span>  
 <span data-ttu-id="46dca-117">Consente di specificare il nome della tabella di traccia dalla quale leggere la traccia.</span><span class="sxs-lookup"><span data-stu-id="46dca-117">Specify the name of the trace table from which the trace should be read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dca-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46dca-118">See Also</span></span>  
 <span data-ttu-id="46dca-119">[Salvare i risultati della traccia in una tabella &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="46dca-119">[Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="46dca-120">[Modelli e autorizzazioni di SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="46dca-120">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="46dca-121">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="46dca-121">Database Engine Tuning Advisor</span></span>](../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
