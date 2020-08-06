---
title: Proprietà traccia (scheda Selezione eventi) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.eventsselection.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: e1892f24-7272-4d5d-8926-6150cc82b2c3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11f4725865d39c21e36f5fd09eaf2afd4cde3017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718635"
---
# <a name="trace-properties-events-selection-tab"></a><span data-ttu-id="4309f-102">Proprietà traccia (scheda Selezione eventi)</span><span class="sxs-lookup"><span data-stu-id="4309f-102">Trace Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="4309f-103">Usare la scheda **Selezione eventi** della finestra di dialogo **Proprietà traccia** per visualizzare o specificare le colonne di dati e gli eventi inseriti nella traccia.</span><span class="sxs-lookup"><span data-stu-id="4309f-103">Use the **Events Selection** tab of the **Trace Properties** dialog box to view or specify traced events and data columns.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4309f-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4309f-104">Options</span></span>  
 <span data-ttu-id="4309f-105">Colonna**Eventi**</span><span class="sxs-lookup"><span data-stu-id="4309f-105">**Events** column</span></span>  
 <span data-ttu-id="4309f-106">È possibile specificare gli eventi inseriti nella traccia selezionando o deselezionando la casella di controllo nella colonna di evento.</span><span class="sxs-lookup"><span data-stu-id="4309f-106">Specify traced events by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="4309f-107">**Gli eventi** sono organizzati in base alla categoria di eventi.</span><span class="sxs-lookup"><span data-stu-id="4309f-107">**Events** are organized by event category.</span></span> <span data-ttu-id="4309f-108">Le classi di evento specificate nel modello vengono selezionate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4309f-108">Event classes specified in the template are automatically selected.</span></span> <span data-ttu-id="4309f-109">Per altre informazioni, vedere [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4309f-109">For more information, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="4309f-110">Colonne di dati</span><span class="sxs-lookup"><span data-stu-id="4309f-110">Data columns</span></span>  
 <span data-ttu-id="4309f-111">È possibile specificare le colonne di dati inseriti nella traccia selezionando la casella che corrisponde all'evento e alla colonna di dati necessari.</span><span class="sxs-lookup"><span data-stu-id="4309f-111">Specify traced data columns by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="4309f-112">Tutte le colonne di evento significative sono selezionate per impostazione predefinita per ogni evento incluso della traccia.</span><span class="sxs-lookup"><span data-stu-id="4309f-112">All relevant event columns are checked by default for each event included in the trace.</span></span>  
  
 <span data-ttu-id="4309f-113">Per specificare i filtri, fare clic sull'intestazione della colonna di dati e immettere i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="4309f-113">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="4309f-114">Le colonne di dati filtrate sono contrassegnate da un'icona di filtro a sinistra dell'etichetta della colonna nella finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="4309f-114">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="4309f-115">Per altre informazioni, vedere [SQL Server Profiler - Modifica filtro](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span><span class="sxs-lookup"><span data-stu-id="4309f-115">For more information, see [SQL Server Profiler - Edit Filter](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span></span>  
  
 <span data-ttu-id="4309f-116">**Mostra tutti gli eventi**</span><span class="sxs-lookup"><span data-stu-id="4309f-116">**Show all events**</span></span>  
 <span data-ttu-id="4309f-117">Consente di visualizzare tutti gli eventi disponibili.</span><span class="sxs-lookup"><span data-stu-id="4309f-117">Show all available events.</span></span> <span data-ttu-id="4309f-118">Per impostazione predefinita, vengono visualizzate solo le righe della griglia **Selezione eventi** selezionate.</span><span class="sxs-lookup"><span data-stu-id="4309f-118">By default, only rows in the **Events Selection** grid that are selected display.</span></span> <span data-ttu-id="4309f-119">Deselezionare questa casella di controllo per nascondere tutti gli eventi non selezionati nella griglia **Selezione eventi** .</span><span class="sxs-lookup"><span data-stu-id="4309f-119">Uncheck this box to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="4309f-120">**Mostra tutte le colonne**</span><span class="sxs-lookup"><span data-stu-id="4309f-120">**Show all columns**</span></span>  
 <span data-ttu-id="4309f-121">Consente di visualizzare tutte le colonne di dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="4309f-121">Show all available data columns.</span></span> <span data-ttu-id="4309f-122">Per impostazione predefinita, vengono visualizzate solo le colonne di dati selezionate.</span><span class="sxs-lookup"><span data-stu-id="4309f-122">By default, only data columns that are selected display.</span></span> <span data-ttu-id="4309f-123">Deselezionare questa casella di controllo per nascondere tutte le colonne di dati non selezionate nella griglia **Selezione eventi** .</span><span class="sxs-lookup"><span data-stu-id="4309f-123">Uncheck this box to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="4309f-124">**Filtri colonne**</span><span class="sxs-lookup"><span data-stu-id="4309f-124">**Column Filters**</span></span>  
 <span data-ttu-id="4309f-125">Consente di aprire la finestra di dialogo **Modifica filtro** ,</span><span class="sxs-lookup"><span data-stu-id="4309f-125">Launches the **Edit Filter** dialog box.</span></span> <span data-ttu-id="4309f-126">utilizzabile per modificare i filtri delle colonne di dati.</span><span class="sxs-lookup"><span data-stu-id="4309f-126">You can use this dialog to edit data column filters.</span></span>  
  
 <span data-ttu-id="4309f-127">**Organizza colonne**</span><span class="sxs-lookup"><span data-stu-id="4309f-127">**Organize Columns**</span></span>  
 <span data-ttu-id="4309f-128">Consente di modificare l'ordine delle colonne nella traccia e di raggruppare i risultati in base a una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="4309f-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4309f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4309f-129">See Also</span></span>  
 <span data-ttu-id="4309f-130">[Specificare eventi e colonne di dati per un file di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4309f-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4309f-131">[Organizzare le colonne visualizzate in una traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4309f-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4309f-132">[Filtrare gli eventi in una traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4309f-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4309f-133">[Visualizza informazioni sui filtri &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4309f-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4309f-134">[Modificare un filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4309f-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4309f-135">[Modelli e autorizzazioni di SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="4309f-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="4309f-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4309f-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
