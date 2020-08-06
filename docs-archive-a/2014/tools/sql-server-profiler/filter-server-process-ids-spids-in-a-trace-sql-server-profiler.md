---
title: Filtrare gli ID del processo server (SPID) in una traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- filters [SQL Server], SPIDs
- traces [SQL Server], filters
ms.assetid: f5945c39-be6b-4632-91cb-92066c80e188
author: stevestein
ms.author: sstein
ms.openlocfilehash: 99ae7eac6f19bd942a04f97b0a7da580eadc9dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723243"
---
# <a name="filter-server-process-ids-spids-in-a-trace-sql-server-profiler"></a><span data-ttu-id="6cbec-102">Filtrare gli ID del processo server (SPID) in una traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="6cbec-102">Filter Server Process IDs (SPIDs) in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="6cbec-103">In questo argomento viene descritta la procedura per il filtraggio degli identificatori del processo server (SPID) in una traccia mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cbec-103">This topic describes how to filter server process identifiers (SPIDs) in a trace by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-system-ids-in-a-trace"></a><span data-ttu-id="6cbec-104">Per filtrare gli ID di sistema in una traccia</span><span class="sxs-lookup"><span data-stu-id="6cbec-104">To filter system IDs in a trace</span></span>  
  
1.  <span data-ttu-id="6cbec-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6cbec-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="6cbec-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="6cbec-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6cbec-107">Se l'opzione **Avvia traccia non appena si crea una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="6cbec-107">if **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="6cbec-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="6cbec-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="6cbec-109">Nella casella **Nome traccia** digitare un nome per la traccia.</span><span class="sxs-lookup"><span data-stu-id="6cbec-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="6cbec-110">Nell'elenco dei nomi di **modello**selezionare un modello di traccia.</span><span class="sxs-lookup"><span data-stu-id="6cbec-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="6cbec-111">Facoltativamente, è possibile specificare un file o una tabella di destinazione in cui salvare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="6cbec-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="6cbec-112">Nella scheda **Selezione eventi**fare clic sull'intestazione di colonna **SPID**per visualizzare la finestra di dialogo **Modifica filtro** .</span><span class="sxs-lookup"><span data-stu-id="6cbec-112">On the **Events Selection**tab, click the **SPID**column heading to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="6cbec-113">È anche possibile fare clic con il pulsante destro del mouse sull'intestazione di colonna e scegliere **Modifica filtro colonne**.</span><span class="sxs-lookup"><span data-stu-id="6cbec-113">You can also right-click the column heading and choose **Edit Column Filter**.</span></span> <span data-ttu-id="6cbec-114">Se non viene visualizzata la colonna **SPID** , selezionare la casella **Mostra tutte le colonne** .</span><span class="sxs-lookup"><span data-stu-id="6cbec-114">If the **SPID** column does not appear, check the **Show all columns** box.</span></span>  
  
6.  <span data-ttu-id="6cbec-115">Nella finestra di dialogo **Modifica filtro** espandere l'operatore di confronto appropriato e immettere uno SPID come valore di confronto.</span><span class="sxs-lookup"><span data-stu-id="6cbec-115">In the **Edit Filter** dialog box, expand the appropriate comparison operator, and enter a SPID as a value for the comparison.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cbec-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cbec-116">See Also</span></span>  
 [<span data-ttu-id="6cbec-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6cbec-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
