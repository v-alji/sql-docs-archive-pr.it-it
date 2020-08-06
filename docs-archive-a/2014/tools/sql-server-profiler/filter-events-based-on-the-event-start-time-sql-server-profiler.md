---
title: Filtrare gli eventi in base all'ora di inizio (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event start times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: e965579e-d006-41a3-89ec-cfd5398c67d2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f652952ec6706580b876e3e9a20f96e62598f81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723247"
---
# <a name="filter-events-based-on-the-event-start-time-sql-server-profiler"></a><span data-ttu-id="286bb-102">Filtrare gli eventi in base all'ora di inizio (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="286bb-102">Filter Events Based on the Event Start Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="286bb-103">In questo argomento viene descritta la procedura per filtrare gli eventi di traccia in base all'ora di inizio mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="286bb-103">This topic describes how to filter trace events based on the event start time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-an-event-based-on-the-event-start-time"></a><span data-ttu-id="286bb-104">Per filtrare un evento in base all'ora di inizio</span><span class="sxs-lookup"><span data-stu-id="286bb-104">To filter an event based on the event start time</span></span>  
  
1.  <span data-ttu-id="286bb-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="286bb-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="286bb-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="286bb-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="286bb-107">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="286bb-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="286bb-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="286bb-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="286bb-109">Nella casella **Nome traccia** digitare un nome per la traccia.</span><span class="sxs-lookup"><span data-stu-id="286bb-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="286bb-110">Nell'elenco dei nomi di **modello**selezionare un modello di traccia.</span><span class="sxs-lookup"><span data-stu-id="286bb-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="286bb-111">Facoltativamente, specificare una destinazione per i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="286bb-111">Optionally specify a destination for the trace results.</span></span>  
  
5.  <span data-ttu-id="286bb-112">Nella scheda **Selezione eventi**fare clic sull'intestazione di colonna **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="286bb-112">On the **Events Selection**tab, click the **StartTime** column heading.</span></span> <span data-ttu-id="286bb-113">È inoltre possibile fare clic con il pulsante destro del mouse sull'intestazione di colonna e quindi scegliere **Modifica filtro colonne** per avviare la finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="286bb-113">You can also right-click the column heading, and then click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span>  
  
6.  <span data-ttu-id="286bb-114">Espandere **maggiore di** o **minore di**e quindi immettere un `datetime` valore nel campo visualizzato sotto l'operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="286bb-114">Expand **Greater than** or **Less than**, and then enter a `datetime` value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286bb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="286bb-115">See Also</span></span>  
 [<span data-ttu-id="286bb-116">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="286bb-116">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
