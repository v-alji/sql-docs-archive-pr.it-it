---
title: Eliminare una traccia (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], deleting
- removing traces
- deleting traces
ms.assetid: a5502814-b281-42dd-b885-5c9368025ae6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3551cff36ef6e2c2e9cc6a4d9b7056ae44cb950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629311"
---
# <a name="delete-a-trace-transact-sql"></a><span data-ttu-id="2994b-102">Eliminare una traccia (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2994b-102">Delete a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="2994b-103">In questo argomento viene illustrata la procedura di utilizzo di stored procedure per eliminare una traccia.</span><span class="sxs-lookup"><span data-stu-id="2994b-103">This topic describes how to use stored procedures to delete a trace.</span></span>  
  
 <span data-ttu-id="2994b-104">Per un esempio dell'uso di stored procedure relative alla traccia, vedere [Creare una traccia &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2994b-104">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span></span>  
  
### <a name="to-delete-a-trace"></a><span data-ttu-id="2994b-105">Per eliminare una traccia</span><span class="sxs-lookup"><span data-stu-id="2994b-105">To delete a trace</span></span>  
  
1.  <span data-ttu-id="2994b-106">Eseguire **sp_trace_setstatus** specificando **@status = 0** per arrestare la traccia.</span><span class="sxs-lookup"><span data-stu-id="2994b-106">Execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="2994b-107">Eseguire **sp_trace_setstatus** specificando **@status = 2** per chiudere la traccia ed eliminare le relative informazioni dal server.</span><span class="sxs-lookup"><span data-stu-id="2994b-107">Execute **sp_trace_setstatus** by specifying **@status = 2** to close the trace and delete its information from the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2994b-108">È necessario che la traccia venga arrestata prima di chiuderla.</span><span class="sxs-lookup"><span data-stu-id="2994b-108">A trace must be stopped first before it can be closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2994b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2994b-109">See Also</span></span>  
 <span data-ttu-id="2994b-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2994b-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="2994b-111">[Stored procedure di sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2994b-111">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="2994b-112">Stored procedure di SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2994b-112">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
