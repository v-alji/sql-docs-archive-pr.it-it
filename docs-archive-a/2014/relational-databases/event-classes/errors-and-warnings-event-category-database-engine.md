---
title: Categoria di eventi Errori e avvisi (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Errors and Warnings event category [SQL Server]
- SQL Server event classes, Errors and Warnings event category
- event classes [SQL Server], Errors and Warnings event category
ms.assetid: 249c19b5-af68-4433-80f6-337395176641
author: stevestein
ms.author: sstein
ms.openlocfilehash: d55f37f5401f60ddfeec340af1ae6d532eb6ad01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719884"
---
# <a name="errors-and-warnings-event-category-database-engine"></a><span data-ttu-id="71756-102">Categoria di eventi Errori e avvisi (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="71756-102">Errors and Warnings Event Category (Database Engine)</span></span>
  <span data-ttu-id="71756-103">La categoria di eventi **Errori e avvisi** include eventi generali relativi a errori e avvisi.</span><span class="sxs-lookup"><span data-stu-id="71756-103">The **Errors and Warnings** event category contains general error and warning events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="71756-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="71756-104">In This Section</span></span>  
  
|<span data-ttu-id="71756-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="71756-105">Topic</span></span>|<span data-ttu-id="71756-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71756-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="71756-107">Classe di evento Attention</span><span class="sxs-lookup"><span data-stu-id="71756-107">Attention Event Class</span></span>](attention-event-class.md)|<span data-ttu-id="71756-108">Indica che è si è verificato un evento **Attention** .</span><span class="sxs-lookup"><span data-stu-id="71756-108">Indicates that an **Attention** event has occurred.</span></span>|  
|[<span data-ttu-id="71756-109">Classe di evento Background Job Error</span><span class="sxs-lookup"><span data-stu-id="71756-109">Background Job Error Event Class</span></span>](background-job-error-event-class.md)|<span data-ttu-id="71756-110">Indica l'interruzione anomala di un processo in background.</span><span class="sxs-lookup"><span data-stu-id="71756-110">Indicates that a background job has terminated abnormally.</span></span>|  
|[<span data-ttu-id="71756-111">Classe di evento Bitmap Warning</span><span class="sxs-lookup"><span data-stu-id="71756-111">Bitmap Warning Event Class</span></span>](bitmap-warning-event-class.md)|<span data-ttu-id="71756-112">Indica che il filtro bitmap è stato disabilitato in una query.</span><span class="sxs-lookup"><span data-stu-id="71756-112">Indicates that bitmap filtering has been disabled in a query.</span></span>|  
|[<span data-ttu-id="71756-113">Classe di evento Blocked Process Report</span><span class="sxs-lookup"><span data-stu-id="71756-113">Blocked Process Report Event Class</span></span>](blocked-process-report-event-class.md)|<span data-ttu-id="71756-114">Indica che un'attività è rimasta bloccata per un periodo di tempo maggiore di quello specificato.</span><span class="sxs-lookup"><span data-stu-id="71756-114">Indicates that a task has been blocked for more than a specified amount of time.</span></span>|  
|[<span data-ttu-id="71756-115">Classe di evento CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="71756-115">CPU Threshold Exceeded Event Class</span></span>](cpu-threshold-exceeded-event-class.md)|<span data-ttu-id="71756-116">Indica che il Resource Governor rileva una query che supera la soglia della CPU specificata.</span><span class="sxs-lookup"><span data-stu-id="71756-116">Indicates that the Resource Governor detects a query that exceeds the specified CPU threshold.</span></span>|  
|[<span data-ttu-id="71756-117">Classe di evento ErrorLog</span><span class="sxs-lookup"><span data-stu-id="71756-117">ErrorLog Event Class</span></span>](errorlog-event-class.md)|<span data-ttu-id="71756-118">Indica che sono stati registrati eventi di errore nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71756-118">Indicates that error events have been logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>|  
|[<span data-ttu-id="71756-119">Classe di evento EventLog</span><span class="sxs-lookup"><span data-stu-id="71756-119">EventLog Event Class</span></span>](eventlog-event-class.md)|<span data-ttu-id="71756-120">Indica la registrazione di eventi nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="71756-120">Indicates that events have been logged in the Windows event log.</span></span>|  
|[<span data-ttu-id="71756-121">Classe di evento Exception</span><span class="sxs-lookup"><span data-stu-id="71756-121">Exception Event Class</span></span>](exception-event-class.md)|<span data-ttu-id="71756-122">Indica la generazione di un'eccezione in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71756-122">Indicates that an exception has occurred in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="71756-123">Classe di evento Exchange Spill</span><span class="sxs-lookup"><span data-stu-id="71756-123">Exchange Spill Event Class</span></span>](exchange-spill-event-class.md)|<span data-ttu-id="71756-124">Indica che i buffer di comunicazione in un piano di query parallelo sono stati scritti nel database tempdb.</span><span class="sxs-lookup"><span data-stu-id="71756-124">Indicates that communication buffers in a parallel query plan have been written to the tempdb database.</span></span>|  
|[<span data-ttu-id="71756-125">Classe di evento Execution Warnings</span><span class="sxs-lookup"><span data-stu-id="71756-125">Execution Warnings Event Class</span></span>](execution-warnings-event-class.md)|<span data-ttu-id="71756-126">Indica la generazione di avvisi di concessione di memoria durante l'esecuzione di un'istruzione o di una stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71756-126">Indicates that memory grant warnings occurred during the execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statement or stored procedure.</span></span>|  
|[<span data-ttu-id="71756-127">Classe di evento Hash Warning</span><span class="sxs-lookup"><span data-stu-id="71756-127">Hash Warning Event Class</span></span>](hash-warning-event-class.md)|<span data-ttu-id="71756-128">Indica il verificarsi di una ricorsione di hash o un hash bailout durante un'operazione di hashing.</span><span class="sxs-lookup"><span data-stu-id="71756-128">Indicates that a hash recursion or hash bailout has occurred during a hashing operation.</span></span>|  
|[<span data-ttu-id="71756-129">Classe di evento Missing Column Statistics</span><span class="sxs-lookup"><span data-stu-id="71756-129">Missing Column Statistics Event Class</span></span>](missing-column-statistics-event-class.md)|<span data-ttu-id="71756-130">Indica che le statistiche di colonna utili per Query Optimizer non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="71756-130">Indicates that column statistics that could have been useful for the optimizer are not available.</span></span>|  
|[<span data-ttu-id="71756-131">Classe di evento Missing Join Predicate</span><span class="sxs-lookup"><span data-stu-id="71756-131">Missing Join Predicate Event Class</span></span>](missing-join-predicate-event-class.md)|<span data-ttu-id="71756-132">Indica che è in esecuzione una query senza predicato di join.</span><span class="sxs-lookup"><span data-stu-id="71756-132">Indicates that a query is being executed that has no join predicate.</span></span>|  
|[<span data-ttu-id="71756-133">Classe di evento Sort Warnings</span><span class="sxs-lookup"><span data-stu-id="71756-133">Sort Warnings Event Class</span></span>](sort-warnings-event-class.md)|<span data-ttu-id="71756-134">Indica le operazioni di ordinamento per cui la memoria disponibile risulta insufficiente.</span><span class="sxs-lookup"><span data-stu-id="71756-134">Indicates that sort operations do not fit into memory.</span></span>|  
|[<span data-ttu-id="71756-135">Classe di evento User Error Message</span><span class="sxs-lookup"><span data-stu-id="71756-135">User Error Message Event Class</span></span>](user-error-message-event-class.md)|<span data-ttu-id="71756-136">Visualizza messaggi di errore per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="71756-136">Displays error messages that are seen by the user.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71756-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71756-137">See Also</span></span>  
 [<span data-ttu-id="71756-138">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71756-138">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
