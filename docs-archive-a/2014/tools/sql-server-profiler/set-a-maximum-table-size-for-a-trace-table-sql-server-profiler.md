---
title: Impostare le dimensioni massime di una tabella di traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- size [SQL Server], trace tables
- maximum table size for traces
ms.assetid: d0ae83e5-1c88-4a2e-be05-2c341280b978
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f48efbe02e300e06faf857ed0fb36ae340ad979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711239"
---
# <a name="set-a-maximum-table-size-for-a-trace-table-sql-server-profiler"></a><span data-ttu-id="8f843-102">Impostare le dimensioni massime di una tabella di traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="8f843-102">Set a Maximum Table Size for a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="8f843-103">In questo argomento viene descritta la procedura per l'impostazione delle dimensioni massime delle tabelle di traccia tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f843-103">This topic describes how to set a maximum table size for trace tables by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-a-maximum-table-size-for-a-trace-table"></a><span data-ttu-id="8f843-104">Per impostare le dimensioni massime di una tabella di traccia</span><span class="sxs-lookup"><span data-stu-id="8f843-104">To set a maximum table size for a trace table</span></span>  
  
1.  <span data-ttu-id="8f843-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f843-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="8f843-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="8f843-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f843-107">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="8f843-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="8f843-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="8f843-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="8f843-109">Nella casella **Nome traccia** digitare un nome per la traccia.</span><span class="sxs-lookup"><span data-stu-id="8f843-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="8f843-110">Nell'elenco **Nome del modello**selezionare un modello di traccia.</span><span class="sxs-lookup"><span data-stu-id="8f843-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="8f843-111">Selezionare la casella di controllo **Salva nella tabella**.</span><span class="sxs-lookup"><span data-stu-id="8f843-111">Select the **Save to table**check box.</span></span>  
  
5.  <span data-ttu-id="8f843-112">Connettersi al server nel quale si desidera archiviare la traccia.</span><span class="sxs-lookup"><span data-stu-id="8f843-112">Connect to the server on which you want the trace to be stored.</span></span>  
  
     <span data-ttu-id="8f843-113">Verrà visualizzata la finestra di dialogo **Tabella di destinazione** .</span><span class="sxs-lookup"><span data-stu-id="8f843-113">The **Destination Table** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="8f843-114">Selezionare un database per la traccia dall'elenco **Database** .</span><span class="sxs-lookup"><span data-stu-id="8f843-114">Select a database for the trace from the **Database** list.</span></span>  
  
7.  <span data-ttu-id="8f843-115">Nella casella **Tabella** digitare o selezionare il nome di una tabella.</span><span class="sxs-lookup"><span data-stu-id="8f843-115">In the **Table** box, type or select a table name.</span></span>  
  
8.  <span data-ttu-id="8f843-116">Selezionare la casella di controllo **Numero massimo di righe** e specificare il numero massimo di righe della tabella di traccia.</span><span class="sxs-lookup"><span data-stu-id="8f843-116">Select the **Set maximum rows** check box, and specify a maximum number of rows for the trace table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f843-117">Quando il numero di righe della tabella supererà il valore massimo specificato, gli eventi di traccia non verranno più registrati.</span><span class="sxs-lookup"><span data-stu-id="8f843-117">When the number of rows in the table exceeds the maximum that you have specified, the trace events are no longer recorded.</span></span> <span data-ttu-id="8f843-118">L'esecuzione della traccia, tuttavia, proseguirà.</span><span class="sxs-lookup"><span data-stu-id="8f843-118">However, tracing continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f843-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f843-119">See Also</span></span>  
 <span data-ttu-id="8f843-120">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="8f843-120">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="8f843-121">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8f843-121">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
