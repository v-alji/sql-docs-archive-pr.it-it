---
title: Proprietà modello di traccia (scheda Selezione eventi) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.tracetemplateproperties.eventsselection.f1
helpviewer_keywords:
- Trace Template Properties dialog box
ms.assetid: 5b202457-ab42-4902-8012-7f3f40aa09f5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: da497db6e9373c63836753dc2be96deb3ce90244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724088"
---
# <a name="trace-template-properties-events-selection-tab"></a><span data-ttu-id="c9381-102">Proprietà modello di traccia (scheda Selezione eventi)</span><span class="sxs-lookup"><span data-stu-id="c9381-102">Trace Template Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="c9381-103">Utilizzare la scheda **Selezione eventi** della finestra di dialogo **Proprietà modello di traccia** per visualizzare, modificare o specificare classi di evento e colonne di dati da includere in un modello di traccia di [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9381-103">Use the **Events Selection** tab of the **Trace Template Properties** dialog box to view, edit, or specify event classes and data columns to include in a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace template.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9381-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c9381-104">Options</span></span>  
 <span data-ttu-id="c9381-105">Colonna**Eventi**</span><span class="sxs-lookup"><span data-stu-id="c9381-105">**Events** column</span></span>  
 <span data-ttu-id="c9381-106">Consente di specificare gli eventi che devono essere inseriti nella traccia selezionando o deselezionando la casella di controllo nella colonna di evento.</span><span class="sxs-lookup"><span data-stu-id="c9381-106">Specify events that should be traced by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="c9381-107">Gli eventi sono organizzati in base alla categoria.</span><span class="sxs-lookup"><span data-stu-id="c9381-107">Events are organized by event category.</span></span>  
  
 <span data-ttu-id="c9381-108">Se è stato selezionato **Basa il nuovo modello sul seguente modello esistente** nella scheda **Generale** , gli eventi vengono selezionati automaticamente in base al modello indicato.</span><span class="sxs-lookup"><span data-stu-id="c9381-108">If you selected **Base new template on existing one** on the **General** tab, events are automatically selected according to the specified template.</span></span> <span data-ttu-id="c9381-109">Per ulteriori informazioni sulle classi degli eventi, vedere [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c9381-109">For more information about event classes, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="c9381-110">Colonne di dati</span><span class="sxs-lookup"><span data-stu-id="c9381-110">Data columns</span></span>  
 <span data-ttu-id="c9381-111">Consente di specificare le colonne di dati che devono essere inserite nella traccia selezionando la casella corrispondente all'evento e alla colonna di dati necessari.</span><span class="sxs-lookup"><span data-stu-id="c9381-111">Specify data columns that should be traced by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="c9381-112">Per ogni evento incluso nella traccia, se la casella di controllo corrispondente all'evento è selezionata, per impostazione predefinita vengono selezionate tutte le relative colonne di dati.</span><span class="sxs-lookup"><span data-stu-id="c9381-112">All relevant event columns are checked by default for each event included in the trace, if the checkbox corresponding to the event is checked.</span></span> <span data-ttu-id="c9381-113">Se è stato selezionato **Basa il nuovo modello sul seguente modello esistente** nella scheda **Generale** , le colonne di dati e i filtri vengono selezionati automaticamente in base al modello indicato.</span><span class="sxs-lookup"><span data-stu-id="c9381-113">If you checked **Base new template on existing one** on the **General** tab, data columns and filters are automatically selected according to the specified template.</span></span>  
  
 <span data-ttu-id="c9381-114">Per specificare i filtri, fare clic sull'intestazione della colonna di dati e immettere i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="c9381-114">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="c9381-115">Le colonne di dati filtrate sono contrassegnate da un'icona di filtro a sinistra dell'etichetta della colonna nella finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="c9381-115">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span>  
  
 <span data-ttu-id="c9381-116">**Mostra tutti gli eventi**</span><span class="sxs-lookup"><span data-stu-id="c9381-116">**Show all events**</span></span>  
 <span data-ttu-id="c9381-117">Consente di visualizzare tutti gli eventi disponibili.</span><span class="sxs-lookup"><span data-stu-id="c9381-117">Show all available events.</span></span> <span data-ttu-id="c9381-118">Se si sta creando un nuovo modello non basato su uno esistente, questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c9381-118">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="c9381-119">Deselezionare questa casella di controllo per nascondere tutti gli eventi non selezionati nella griglia **Selezione eventi** .</span><span class="sxs-lookup"><span data-stu-id="c9381-119">Uncheck to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="c9381-120">**Mostra tutte le colonne**</span><span class="sxs-lookup"><span data-stu-id="c9381-120">**Show all columns**</span></span>  
 <span data-ttu-id="c9381-121">Consente di visualizzare tutte le colonne di dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="c9381-121">Show all available data columns.</span></span> <span data-ttu-id="c9381-122">Se si sta creando un nuovo modello non basato su uno esistente, questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c9381-122">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="c9381-123">Deselezionare questa casella di controllo per nascondere tutte le colonne di dati non selezionate nella griglia **Selezione eventi** .</span><span class="sxs-lookup"><span data-stu-id="c9381-123">Uncheck to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="c9381-124">**Filtri colonne**</span><span class="sxs-lookup"><span data-stu-id="c9381-124">**Column Filters**</span></span>  
 <span data-ttu-id="c9381-125">Consente di aprire la finestra di dialogo **Modifica filtro** , che visualizza un'icona di filtro a sinistra dell'etichetta della colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="c9381-125">Launches the **Edit Filter** dialog box, which displays a filter icon to the left of the data column label.</span></span> <span data-ttu-id="c9381-126">Utilizzare la finestra di dialogo **Modifica filtro** per modificare i filtri delle colonne di dati.</span><span class="sxs-lookup"><span data-stu-id="c9381-126">Use the **Edit Filter** dialog box to edit data column filters.</span></span>  
  
 <span data-ttu-id="c9381-127">**Organizza colonne**</span><span class="sxs-lookup"><span data-stu-id="c9381-127">**Organize Columns**</span></span>  
 <span data-ttu-id="c9381-128">Consente di modificare l'ordine delle colonne nella traccia e di raggruppare i risultati in base a una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="c9381-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9381-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9381-129">See Also</span></span>  
 <span data-ttu-id="c9381-130">[Specificare eventi e colonne di dati per un file di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c9381-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c9381-131">[Organizzare le colonne visualizzate in una traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c9381-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c9381-132">[Filtrare gli eventi in una traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c9381-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c9381-133">[Visualizza informazioni sui filtri &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c9381-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c9381-134">[Modificare un filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c9381-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c9381-135">[Modelli e autorizzazioni di SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c9381-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="c9381-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c9381-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
