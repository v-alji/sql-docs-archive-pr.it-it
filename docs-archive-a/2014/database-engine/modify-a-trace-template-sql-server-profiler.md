---
title: Modificare un modello di traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- modifying traces
ms.assetid: b81df2a1-e202-43d8-92b0-0beb145f0116
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2a93baedb1875ac740e74065ae7188f9b576e083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624896"
---
# <a name="modify-a-trace-template-sql-server-profiler"></a><span data-ttu-id="c10c6-102">Modificare un modello di traccia (SQL Profiler)</span><span class="sxs-lookup"><span data-stu-id="c10c6-102">Modify a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="c10c6-103">In questo argomento viene descritto come modificare un modello di traccia utilizzando [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c10c6-103">This topic describes how to modify a trace template by using [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-modify-a-trace-template"></a><span data-ttu-id="c10c6-104">Per modificare un modello di traccia</span><span class="sxs-lookup"><span data-stu-id="c10c6-104">To modify a trace template</span></span>  
  
1.  <span data-ttu-id="c10c6-105">Scegliere **Modelli** dal menu **File**, quindi fare clic su **Modifica modello**.</span><span class="sxs-lookup"><span data-stu-id="c10c6-105">On the **File** menu, point to **Templates**, and then click **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="c10c6-106">Nella scheda **Generale** della finestra di dialogo **Proprietà modello di traccia** è possibile modificare il tipo di server e il nome del modello oppure scegliere di usare un modello predefinito per il tipo di server.</span><span class="sxs-lookup"><span data-stu-id="c10c6-106">In the **Trace Template Properties** dialog box, on the **General** tab, you can modify the server type and template name, or choose to use a default template for the server type.</span></span>  
  
3.  <span data-ttu-id="c10c6-107">Nella scheda **Selezione eventi**utilizzare il controllo griglia per aggiungere o rimuovere eventi e colonne di dati dal file di traccia, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c10c6-107">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows.</span></span>  
  
    -   <span data-ttu-id="c10c6-108">Per aggiungere un evento, espandere la categoria di eventi appropriata nella colonna **Eventi** e quindi selezionare il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c10c6-108">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="c10c6-109">Quando si aggiunge un evento, tutte le colonne di dati significative vengono incluse per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c10c6-109">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="c10c6-110">Per rimuovere una colonna di dati per un evento da una traccia, deselezionare la casella di controllo nella colonna di dati per l'evento.</span><span class="sxs-lookup"><span data-stu-id="c10c6-110">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="c10c6-111">Per aggiungere i filtri, fare clic sul nome della colonna di dati e specificare i criteri del filtro nella finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="c10c6-111">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="c10c6-112">È anche possibile fare clic con il pulsante destro del mouse sul nome della colonna di dati e scegliere **Modifica filtro colonne** per accedere alla finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="c10c6-112">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="c10c6-113">Fare clic su **OK** per aggiungere il filtro.</span><span class="sxs-lookup"><span data-stu-id="c10c6-113">Click **OK** to add the filter.</span></span>  
  
4.  <span data-ttu-id="c10c6-114">Fare clic su **Salva**oppure su **Salva con nome**per salvare il modello di traccia con un altro nome.</span><span class="sxs-lookup"><span data-stu-id="c10c6-114">Click **Save**, or click **Save As**to save the trace template under another name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10c6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c10c6-115">See Also</span></span>  
 <span data-ttu-id="c10c6-116">[Specificare eventi e colonne di dati per un file di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c10c6-116">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c10c6-117">[Derivare un modello da una traccia in esecuzione &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c10c6-117">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c10c6-118">[Derivare un modello da un file di traccia o da una tabella di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c10c6-118">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c10c6-119">[Modelli e autorizzazioni di SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c10c6-119">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="c10c6-120">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c10c6-120">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
