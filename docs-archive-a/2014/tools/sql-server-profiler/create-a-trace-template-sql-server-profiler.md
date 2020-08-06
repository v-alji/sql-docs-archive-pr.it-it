---
title: Creare un modello di traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- saving trace template
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 355f97c7fecd8a9e31f10de881d1ae6df3b8f122
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711259"
---
# <a name="create-a-trace-template-sql-server-profiler"></a><span data-ttu-id="dab7a-102">Creare un modello di traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="dab7a-102">Create a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="dab7a-103">In questo argomento viene descritto come creare un nuovo modello di traccia utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dab7a-103">This topic describes how to create a new trace template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-trace-template"></a><span data-ttu-id="dab7a-104">Per creare un modello di traccia</span><span class="sxs-lookup"><span data-stu-id="dab7a-104">To create a trace template</span></span>  
  
1.  <span data-ttu-id="dab7a-105">Scegliere **Modelli** dal menu **File**e quindi fare clic su **Nuovo modello**.</span><span class="sxs-lookup"><span data-stu-id="dab7a-105">On the **File** menu, point to **Templates**, and then click **New Template**.</span></span>  
  
2.  <span data-ttu-id="dab7a-106">Nella finestra di dialogo **Proprietà modello di traccia** selezionare il tipo di server nell'elenco **Tipo server**.</span><span class="sxs-lookup"><span data-stu-id="dab7a-106">In the **Trace Template Properties** dialog box, select a server type from the **Select server type**list.</span></span>  
  
3.  <span data-ttu-id="dab7a-107">Nella casella **Nome nuovo modello** immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="dab7a-107">In the **New template name** box, enter a template name.</span></span>  
  
4.  <span data-ttu-id="dab7a-108">Facoltativamente, selezionare la casella di controllo **Basa il nuovo modello sul seguente modello esistente**e quindi fare clic su un modello nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dab7a-108">Optionally, click **Base new template on existing one**, and then select a template from the list.</span></span>  
  
     <span data-ttu-id="dab7a-109">Tutti gli eventi, le colonne di dati e i filtri vengono impostati inizialmente come specificato nel modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="dab7a-109">All events, data columns, and filters are initially set as specified in the selected template.</span></span>  
  
5.  <span data-ttu-id="dab7a-110">Facoltativamente, selezionare la casella di controllo **Usa come modello predefinito per il tipo di server selezionato**.</span><span class="sxs-lookup"><span data-stu-id="dab7a-110">Optionally, click **Use as a default template for selected server type**.</span></span>  
  
6.  <span data-ttu-id="dab7a-111">Nella scheda **Selezione eventi** aggiungere, rimuovere o modificare eventi, colonne di dati o filtri.</span><span class="sxs-lookup"><span data-stu-id="dab7a-111">On the **Events Selection** tab, add, remove, or modify events, data columns, or filters.</span></span>  
  
7.  <span data-ttu-id="dab7a-112">Nella scheda **Selezione eventi**usare il controllo griglia per aggiungere o rimuovere eventi e colonne di dati dal file di traccia, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="dab7a-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows:</span></span>  
  
    -   <span data-ttu-id="dab7a-113">Per aggiungere un evento, espandere la categoria di eventi appropriata nella colonna **Eventi** e quindi selezionare il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="dab7a-113">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="dab7a-114">Quando si aggiunge un evento, tutte le colonne di dati significative vengono incluse per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dab7a-114">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="dab7a-115">Per rimuovere una colonna di dati per un evento da una traccia, deselezionare la casella di controllo nella colonna di dati per l'evento.</span><span class="sxs-lookup"><span data-stu-id="dab7a-115">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="dab7a-116">Per aggiungere i filtri, fare clic sul nome della colonna di dati e specificare i criteri del filtro nella finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="dab7a-116">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="dab7a-117">È anche possibile fare clic con il pulsante destro del mouse sul nome della colonna di dati e scegliere **Modifica filtro colonne** per accedere alla finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="dab7a-117">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="dab7a-118">Fare clic su **OK** per aggiungere il filtro.</span><span class="sxs-lookup"><span data-stu-id="dab7a-118">Click **OK** to add the filter.</span></span>  
  
8.  <span data-ttu-id="dab7a-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dab7a-119">Click **Save.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab7a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dab7a-120">See Also</span></span>  
 <span data-ttu-id="dab7a-121">[Specificare eventi e colonne di dati per un file di traccia &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="dab7a-121">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="dab7a-122">[Derivare un modello da una traccia in esecuzione &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="dab7a-122">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="dab7a-123">[Derivare un modello da un file di traccia o da una tabella di traccia &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="dab7a-123">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="dab7a-124">[Modelli e autorizzazioni di SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="dab7a-124">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="dab7a-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="dab7a-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
