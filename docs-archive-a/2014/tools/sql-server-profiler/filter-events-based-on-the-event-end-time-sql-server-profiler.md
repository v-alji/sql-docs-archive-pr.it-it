---
title: Filtrare gli eventi in base all'ora di fine (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event end times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 74628f9e-2d39-496a-a443-0a3887db223d
author: stevestein
ms.author: sstein
ms.openlocfilehash: d25d8e1adbd95f48d88fd1516c48dcc0f8374a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725171"
---
# <a name="filter-events-based-on-the-event-end-time-sql-server-profiler"></a><span data-ttu-id="57763-102">Filtrare eventi in base all'ora di fine (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="57763-102">Filter Events Based on the Event End Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="57763-103">In questo argomento viene illustrata la procedura per filtrare gli eventi di traccia in base all'ora di fine dell'evento tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57763-103">This topic describes how to filter trace events based on the event ending time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-events-based-on-the-event-end-time"></a><span data-ttu-id="57763-104">Per filtrare gli eventi in base all'ora di fine</span><span class="sxs-lookup"><span data-stu-id="57763-104">To filter events based on the event end time</span></span>  
  
1.  <span data-ttu-id="57763-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57763-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="57763-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="57763-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57763-107">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="57763-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="57763-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="57763-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="57763-109">Nella finestra di dialogo **Proprietà traccia** verificare che sia selezionata la scheda **Generale** e quindi immettere un nome nella casella di testo **Nome traccia** .</span><span class="sxs-lookup"><span data-stu-id="57763-109">In the **Trace Properties** dialog box, make sure the **General** tab is selected, and enter a name in the **TraceName** text box.</span></span>  
  
3.  <span data-ttu-id="57763-110">Selezionare un modello di traccia nell'elenco **Modello**.</span><span class="sxs-lookup"><span data-stu-id="57763-110">From the **Use the template**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="57763-111">Facoltativamente, è possibile specificare un file o una tabella di destinazione in cui salvare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="57763-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="57763-112">Nella scheda **Selezione eventi**fare clic sulla colonna di dati **EndTime** per aprire la finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="57763-112">On the **Events Selection**tab, click the **EndTime** data column to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="57763-113">È anche possibile fare clic con il pulsante destro del mouse sull'intestazione di colonna e scegliere **Modifica filtro colonne**.</span><span class="sxs-lookup"><span data-stu-id="57763-113">You can also right-click the column heading, and select **Edit Column Filter**.</span></span>  
  
6.  <span data-ttu-id="57763-114">Espandere **maggiore di** o **minore di**e immettere un `datetime` valore nel campo visualizzato sotto l'operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="57763-114">Expand **Greater than** or **Less than**, and enter a `datetime`value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57763-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57763-115">See Also</span></span>  
 <span data-ttu-id="57763-116">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="57763-116">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="57763-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="57763-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
