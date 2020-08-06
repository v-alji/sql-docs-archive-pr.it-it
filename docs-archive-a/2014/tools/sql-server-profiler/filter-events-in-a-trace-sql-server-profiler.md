---
title: Filtrare eventi in una traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 0fd63573-3b35-4f67-9e1e-ed9aabee11a8
author: stevestein
ms.author: sstein
ms.openlocfilehash: fef9dd6956d407011261c54f796a751a0bf94941
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723248"
---
# <a name="filter-events-in-a-trace-sql-server-profiler"></a><span data-ttu-id="2b698-102">Filtrare eventi in una traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="2b698-102">Filter Events in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="2b698-103">I filtri consentono di limitare gli eventi raccolti in una traccia.</span><span class="sxs-lookup"><span data-stu-id="2b698-103">Filters limit the events collected in a trace.</span></span> <span data-ttu-id="2b698-104">Se non si imposta un filtro, tutti gli eventi delle classi di evento selezionate vengono restituiti nell'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="2b698-104">If a filter is not set, all events of the selected event classes are returned in the trace output.</span></span> <span data-ttu-id="2b698-105">L'impostazione di un filtro per una traccia non è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="2b698-105">It is not mandatory to set a filter for a trace.</span></span> <span data-ttu-id="2b698-106">Un filtro consente, tuttavia, di ridurre l'overhead che si verifica durante una traccia,</span><span class="sxs-lookup"><span data-stu-id="2b698-106">However, a filter minimizes the overhead that is incurred during tracing.</span></span>  
  
 <span data-ttu-id="2b698-107">Per aggiungere filtri alle definizioni della traccia, usare la scheda **Selezione eventi** della finestra di dialogo **Proprietà traccia** o **Proprietà modello di traccia** .</span><span class="sxs-lookup"><span data-stu-id="2b698-107">You add filters to trace definitions by using the **Events Selection** tab of the **Trace Properties** or **Trace Template Properties** dialog box.</span></span>  
  
### <a name="to-filter-events-in-a-trace"></a><span data-ttu-id="2b698-108">Per filtrare gli eventi in una traccia</span><span class="sxs-lookup"><span data-stu-id="2b698-108">To filter events in a trace</span></span>  
  
1.  <span data-ttu-id="2b698-109">Nella finestra di dialogo **Proprietà traccia** o **Proprietà modello di traccia** fare clic sulla scheda **Selezione eventi** .</span><span class="sxs-lookup"><span data-stu-id="2b698-109">In the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="2b698-110">La scheda **Selezione eventi** contiene un controllo griglia,</span><span class="sxs-lookup"><span data-stu-id="2b698-110">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="2b698-111">ovvero una tabella che include tutte le classi di evento tracciabili.</span><span class="sxs-lookup"><span data-stu-id="2b698-111">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="2b698-112">La tabella contiene una riga per ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="2b698-112">The table contains one row for each event class.</span></span> <span data-ttu-id="2b698-113">Le classi di evento possono differire leggermente a seconda del tipo e della versione del server cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="2b698-113">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="2b698-114">Le classi di eventi sono identificate nella colonna **Eventi**della griglia e sono raggruppate per categoria di eventi.</span><span class="sxs-lookup"><span data-stu-id="2b698-114">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="2b698-115">Nelle altre colonne sono elencate le colonne di dati che possono essere restituite per ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="2b698-115">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="2b698-116">Fare clic su **Filtri colonne**.</span><span class="sxs-lookup"><span data-stu-id="2b698-116">Click **Column Filters.**</span></span>  
  
     <span data-ttu-id="2b698-117">Viene visualizzata la finestra di dialogo **Modifica filtro**.</span><span class="sxs-lookup"><span data-stu-id="2b698-117">The **Edit Filter**dialog box appears.</span></span> <span data-ttu-id="2b698-118">Nella finestra di dialogo **Modifica filtro**è disponibile un elenco di operatori di confronto che consentono di filtrare gli eventi in una traccia.</span><span class="sxs-lookup"><span data-stu-id="2b698-118">The **Edit Filter**dialog box contains a list of comparison operators that you can use to filter events in a trace.</span></span>  
  
3.  <span data-ttu-id="2b698-119">Per applicare un filtro, fare clic sull'operatore di confronto e immettere il valore da utilizzare per il filtro.</span><span class="sxs-lookup"><span data-stu-id="2b698-119">To apply a filter, click the comparison operator, and type a value to use for the filter.</span></span>  
  
4.  <span data-ttu-id="2b698-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b698-120">Click **OK**.</span></span>  
  
 <span data-ttu-id="2b698-121">**Considerazioni:**</span><span class="sxs-lookup"><span data-stu-id="2b698-121">**Considerations:**</span></span>  
  
-   <span data-ttu-id="2b698-122">Se si impostano condizioni di filtro sulle colonne di dati **StartTime** ed **EndTime** della scheda Selezione eventi, assicurarsi che:</span><span class="sxs-lookup"><span data-stu-id="2b698-122">If you set filter conditions on the **StartTime** and **EndTime** data columns of the Events Selection tab, then make sure that:</span></span>  
  
    -   <span data-ttu-id="2b698-123">Il formato della data immessa sia uguale al seguente: `YYYY/MM/DD HH:mm:sec`.</span><span class="sxs-lookup"><span data-stu-id="2b698-123">The date you enter matches this format: `YYYY/MM/DD HH:mm:sec`.</span></span>  
  
         <span data-ttu-id="2b698-124">-OPPURE-</span><span class="sxs-lookup"><span data-stu-id="2b698-124">-OR-</span></span>  
  
    -   <span data-ttu-id="2b698-125">L'opzione**Visualizza valori di data e ora in base alle impostazioni internazionali** sia selezionata nella finestra di dialogo **Opzioni generali** .</span><span class="sxs-lookup"><span data-stu-id="2b698-125">**Use regional settings to display date and time values** is checked in the **General Options** dialog box.</span></span> <span data-ttu-id="2b698-126">Per visualizzare la finestra di dialogo **Opzioni generali**, scegliere [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Opzioni**dal menu**Strumenti**di**.</span><span class="sxs-lookup"><span data-stu-id="2b698-126">To view the **General Options** dialog box, on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Tools** menu, click **Option**.</span></span>  
  
         <span data-ttu-id="2b698-127">-e-</span><span class="sxs-lookup"><span data-stu-id="2b698-127">-AND-</span></span>  
  
    -   <span data-ttu-id="2b698-128">La data immessa sia compresa tra 1 gennaio 1753 e 31 dicembre 9999.</span><span class="sxs-lookup"><span data-stu-id="2b698-128">The date you enter is between January 1, 1753 and December 31, 9999.</span></span>  
  
-   <span data-ttu-id="2b698-129">Se si tracciano eventi con l'utilità **osql** o **sqlcmd** , aggiungere sempre **%** ai filtri nella colonna di dati **TextData** .</span><span class="sxs-lookup"><span data-stu-id="2b698-129">If tracing events from the **osql** utility or from the **sqlcmd** utility, always append **%** to filters on the **TextData** data column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b698-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b698-130">See Also</span></span>  
 [<span data-ttu-id="2b698-131">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="2b698-131">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
