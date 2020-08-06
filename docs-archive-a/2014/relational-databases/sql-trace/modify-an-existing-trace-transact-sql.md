---
title: Modificare una traccia esistente (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 55b8172ef8e6188059c484ab41f1a719e0e9f8c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624547"
---
# <a name="modify-an-existing-trace-transact-sql"></a><span data-ttu-id="01276-102">Modificare una traccia esistente (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="01276-102">Modify an Existing Trace (Transact-SQL)</span></span>
  <span data-ttu-id="01276-103">In questo argomento viene descritto come utilizzare stored procedure per modificare una traccia esistente.</span><span class="sxs-lookup"><span data-stu-id="01276-103">This topic describes how to use stored procedures to modify an existing trace.</span></span>  
  
### <a name="to-modify-an-existing-trace"></a><span data-ttu-id="01276-104">Per modificare una traccia esistente</span><span class="sxs-lookup"><span data-stu-id="01276-104">To modify an existing trace</span></span>  
  
1.  <span data-ttu-id="01276-105">Se la traccia è già in esecuzione, eseguire **sp_trace_setstatus** specificando **@status = 0** per arrestarla.</span><span class="sxs-lookup"><span data-stu-id="01276-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="01276-106">Per modificare eventi di traccia, eseguire **sp_trace_setevent** usando i parametri per specificare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="01276-106">To modify trace events, execute **sp_trace_setevent** by specifying the changes through the parameters.</span></span> <span data-ttu-id="01276-107">Nell'ordine i parametri sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="01276-107">Listed in order, the parameters are:</span></span>  
  
    -   <span data-ttu-id="01276-108">**@traceid**(ID traccia)</span><span class="sxs-lookup"><span data-stu-id="01276-108">**@traceid** (Trace ID)</span></span>  
  
    -   <span data-ttu-id="01276-109">**@eventid**(ID evento)</span><span class="sxs-lookup"><span data-stu-id="01276-109">**@eventid** (Event ID)</span></span>  
  
    -   <span data-ttu-id="01276-110">**@columnid**(ID colonna)</span><span class="sxs-lookup"><span data-stu-id="01276-110">**@columnid** (Column ID)</span></span>  
  
    -   <span data-ttu-id="01276-111">**@on**IN</span><span class="sxs-lookup"><span data-stu-id="01276-111">**@on** (ON)</span></span>  
  
     <span data-ttu-id="01276-112">Quando si modifica il **@on** parametro, tenere presente l'interazione con il **@columnid** parametro:</span><span class="sxs-lookup"><span data-stu-id="01276-112">When you modify the **@on** parameter, keep in mind its interaction with the **@columnid** parameter:</span></span>  
  
    |<span data-ttu-id="01276-113">ATTIVA</span><span class="sxs-lookup"><span data-stu-id="01276-113">ON</span></span>|<span data-ttu-id="01276-114">ID colonna</span><span class="sxs-lookup"><span data-stu-id="01276-114">Column ID</span></span>|<span data-ttu-id="01276-115">Risultato</span><span class="sxs-lookup"><span data-stu-id="01276-115">Result</span></span>|  
    |--------|---------------|------------|  
    |<span data-ttu-id="01276-116">ON (**1**)</span><span class="sxs-lookup"><span data-stu-id="01276-116">ON (**1**)</span></span>|<span data-ttu-id="01276-117">NULL</span><span class="sxs-lookup"><span data-stu-id="01276-117">NULL</span></span>|<span data-ttu-id="01276-118">L'evento viene abilitato.</span><span class="sxs-lookup"><span data-stu-id="01276-118">Event is turned on.</span></span> <span data-ttu-id="01276-119">Tutte le colonne vengono cancellate.</span><span class="sxs-lookup"><span data-stu-id="01276-119">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="01276-120">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="01276-120">NOT NULL</span></span>|<span data-ttu-id="01276-121">La colonna viene abilitata per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="01276-121">Column is turned on for the specified event.</span></span>|  
    |<span data-ttu-id="01276-122">OFF (**0**)</span><span class="sxs-lookup"><span data-stu-id="01276-122">OFF (**0**)</span></span>|<span data-ttu-id="01276-123">NULL</span><span class="sxs-lookup"><span data-stu-id="01276-123">NULL</span></span>|<span data-ttu-id="01276-124">L'evento viene disabilitato.</span><span class="sxs-lookup"><span data-stu-id="01276-124">Event is turned off.</span></span> <span data-ttu-id="01276-125">Tutte le colonne vengono cancellate.</span><span class="sxs-lookup"><span data-stu-id="01276-125">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="01276-126">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="01276-126">NOT NULL</span></span>|<span data-ttu-id="01276-127">La colonna viene disabilitata per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="01276-127">Column is turned off for the specified event.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="01276-128">A differenza di quanto avviene con le normali stored procedure, i parametri di tutte le stored procedure di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>) sono fortemente tipizzati e non supportano la conversione automatica del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="01276-128">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="01276-129">Se tali parametri non vengono chiamati con i tipi di dati corretti per i parametri di input, come indicato nella descrizione dell'argomento, la stored procedure restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="01276-129">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  

## <a name="see-also"></a><span data-ttu-id="01276-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01276-130">See Also</span></span>  
 <span data-ttu-id="01276-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01276-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="01276-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01276-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="01276-133">[Stored procedure di sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01276-133">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="01276-134">Stored procedure di SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="01276-134">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
