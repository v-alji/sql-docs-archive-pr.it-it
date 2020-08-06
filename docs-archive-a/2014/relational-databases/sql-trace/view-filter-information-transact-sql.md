---
title: Visualizzare informazioni sui filtri (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: b7e52c13-8c83-47c2-8cd0-af7a49eceb5c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d94a7b4a73c264c1fb3a950aa1c9615a73db956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726819"
---
# <a name="view-filter-information-transact-sql"></a><span data-ttu-id="5a5ba-102">Visualizzare informazioni sui filtri (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5a5ba-102">View Filter Information (Transact-SQL)</span></span>
  <span data-ttu-id="5a5ba-103">In questo argomento viene illustrata la procedura di utilizzo delle funzioni predefinite per la visualizzazione delle informazioni sui filtri di traccia.</span><span class="sxs-lookup"><span data-stu-id="5a5ba-103">This topic describes how to use built-in functions to view trace filter information.</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="5a5ba-104">Per visualizzare informazioni sui filtri</span><span class="sxs-lookup"><span data-stu-id="5a5ba-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="5a5ba-105">Eseguire **fn_trace_getfilterinfo** specificando l'ID della traccia per cui vuole ottenere informazioni sui filtri.</span><span class="sxs-lookup"><span data-stu-id="5a5ba-105">Execute **fn_trace_getfilterinfo** by specifying the ID of the trace about which filter information is needed.</span></span> <span data-ttu-id="5a5ba-106">La funzione restituisce una tabella con l'elenco dei filtri, le colonne cui i filtri sono applicati e i valori ai quali il filtro si applica.</span><span class="sxs-lookup"><span data-stu-id="5a5ba-106">This function returns a table that lists the filters, the columns on which the filters are applied, and the values on which the filter is applied.</span></span>  
  
     <span data-ttu-id="5a5ba-107">Richiamare la funzione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="5a5ba-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getfilterinfo(trace_id)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5a5ba-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a5ba-108">See Also</span></span>  
 <span data-ttu-id="5a5ba-109">[sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a5ba-109">[sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql) </span></span>  
 <span data-ttu-id="5a5ba-110">[Stored procedure di sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a5ba-110">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="5a5ba-111">Stored procedure di SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5a5ba-111">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
