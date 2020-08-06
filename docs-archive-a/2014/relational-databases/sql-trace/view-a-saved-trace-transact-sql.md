---
title: Visualizzare una traccia salvata (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], viewing
- displaying traces
- viewing traces
ms.assetid: 3a95a816-aa89-4d5f-858c-968a9cb3ee87
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8b67760d575b651b089a6936adc945d74a1c62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726823"
---
# <a name="view-a-saved-trace-transact-sql"></a><span data-ttu-id="d0a1b-102">Visualizzare una traccia salvata (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d0a1b-102">View a Saved Trace (Transact-SQL)</span></span>
  <span data-ttu-id="d0a1b-103">In questo argomento viene illustrato l'utilizzo delle funzioni predefinite per visualizzare una traccia salvata.</span><span class="sxs-lookup"><span data-stu-id="d0a1b-103">This topic describes how to use built-in functions to view a saved trace.</span></span>  
  
### <a name="to-view-a-specific-trace"></a><span data-ttu-id="d0a1b-104">Per visualizzare una traccia specifica</span><span class="sxs-lookup"><span data-stu-id="d0a1b-104">To view a specific trace</span></span>  
  
1.  <span data-ttu-id="d0a1b-105">Eseguire **fn_trace_getinfo** specificando l'ID della traccia su cui si vuole ottenere informazioni.</span><span class="sxs-lookup"><span data-stu-id="d0a1b-105">Execute **fn_trace_getinfo** by specifying the ID of the trace about which information is needed.</span></span> <span data-ttu-id="d0a1b-106">Questa funzione restituisce una tabella in cui sono indicate la traccia, la proprietà della traccia e le informazioni sulla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0a1b-106">This function returns a table that lists the trace, trace property, and information about the property.</span></span>  
  
     <span data-ttu-id="d0a1b-107">Richiamare la funzione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d0a1b-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(trace_id)  
    ```  
  
### <a name="to-view-all-existing-traces"></a><span data-ttu-id="d0a1b-108">Per visualizzare tutte le tracce esistenti</span><span class="sxs-lookup"><span data-stu-id="d0a1b-108">To view all existing traces</span></span>  
  
1.  <span data-ttu-id="d0a1b-109">Eseguire **fn_trace_getinfo** specificando `0` o `default`.</span><span class="sxs-lookup"><span data-stu-id="d0a1b-109">Execute **fn_trace_getinfo** by specifying `0` or `default`.</span></span> <span data-ttu-id="d0a1b-110">Questa funzione restituisce una tabella in cui sono indicate tutte le tracce, le relative proprietà e le informazioni su tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0a1b-110">This function returns a table that lists all the traces, their properties, and information about these properties.</span></span>  
  
     <span data-ttu-id="d0a1b-111">Di seguito è illustrato come richiamare la funzione:</span><span class="sxs-lookup"><span data-stu-id="d0a1b-111">Invoke the function as follows:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(default)  
    ```  
  
## <a name="net-framework-security"></a><span data-ttu-id="d0a1b-112">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d0a1b-112">.NET Framework Security</span></span>  
 <span data-ttu-id="d0a1b-113">Per eseguire la funzione predefinita **fn_trace_getinfo**, è necessaria l'autorizzazione seguente:</span><span class="sxs-lookup"><span data-stu-id="d0a1b-113">To run the built-in function **fn_trace_getinfo**, the user needs the following permission:</span></span>  
  
 <span data-ttu-id="d0a1b-114">ALTER TRACE nel server.</span><span class="sxs-lookup"><span data-stu-id="d0a1b-114">ALTER TRACE on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a1b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0a1b-115">See Also</span></span>  
 <span data-ttu-id="d0a1b-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0a1b-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span></span>  
 [<span data-ttu-id="d0a1b-117">Visualizzare e analizzare le tracce con SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d0a1b-117">View and Analyze Traces with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/view-and-analyze-traces-with-sql-server-profiler.md)  
  
  
