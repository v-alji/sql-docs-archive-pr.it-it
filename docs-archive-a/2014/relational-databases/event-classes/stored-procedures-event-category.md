---
title: Categoria di eventi Stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Stored Procedures event category [SQL Server]
- SQL Server event classes, Stored Procedures event category
- event classes [SQL Server], Stored Procedures event category
ms.assetid: 71bebaa3-a05a-4695-b349-078cecd0949a
author: stevestein
ms.author: sstein
ms.openlocfilehash: df2e0d9a4c077ff16eba09bc5ebb6447d5d27595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726967"
---
# <a name="stored-procedures-event-category"></a><span data-ttu-id="5f14e-102">Categoria di eventi Stored procedure</span><span class="sxs-lookup"><span data-stu-id="5f14e-102">Stored Procedures Event Category</span></span>
  <span data-ttu-id="5f14e-103">La categoria di eventi **Stored Procedure** contiene eventi stored procedure generali.</span><span class="sxs-lookup"><span data-stu-id="5f14e-103">The **Stored Procedures** event category contains general stored procedure events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f14e-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5f14e-104">In This Section</span></span>  
  
|<span data-ttu-id="5f14e-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="5f14e-105">Topic</span></span>|<span data-ttu-id="5f14e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f14e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5f14e-107">Classe di evento RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="5f14e-107">RPC:Completed Event Class</span></span>](rpc-completed-event-class.md)|<span data-ttu-id="5f14e-108">Indica il completamento di una chiamata di procedura remota (RPC).</span><span class="sxs-lookup"><span data-stu-id="5f14e-108">Indicates that a remote procedure call (RPC) has been completed.</span></span>|  
|[<span data-ttu-id="5f14e-109">Classe di evento PreConnect:Completed</span><span class="sxs-lookup"><span data-stu-id="5f14e-109">PreConnect:Completed Event Class</span></span>](preconnect-completed-event-class.md)|<span data-ttu-id="5f14e-110">Indica la fine dell'esecuzione di una funzione di classificazione di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="5f14e-110">Indicates when the Resource Governor classifier function finishes execution.</span></span>|  
|[<span data-ttu-id="5f14e-111">Classe di evento PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="5f14e-111">PreConnect:Starting Event Class</span></span>](preconnect-starting-event-class.md)|<span data-ttu-id="5f14e-112">Indica l'avvio dell'esecuzione di una funzione di classificazione di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="5f14e-112">Indicates when the Resource Governor classifier function starts execution.</span></span>|  
|[<span data-ttu-id="5f14e-113">Classe di evento RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="5f14e-113">RPC Output Parameter Event Class</span></span>](rpc-output-parameter-event-class.md)|<span data-ttu-id="5f14e-114">Traccia i valori di output dei parametri delle chiamate di procedura remota dopo l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5f14e-114">Traces the output parameter values of remote procedure calls after execution.</span></span>|  
|[<span data-ttu-id="5f14e-115">Classe di evento RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="5f14e-115">RPC:Starting Event Class</span></span>](rpc-starting-event-class.md)|<span data-ttu-id="5f14e-116">Indica l'avvio di una chiamata di procedura remota.</span><span class="sxs-lookup"><span data-stu-id="5f14e-116">Indicates that a remote procedure call is starting.</span></span>|  
|[<span data-ttu-id="5f14e-117">Classe di evento SP:CacheHit</span><span class="sxs-lookup"><span data-stu-id="5f14e-117">SP:CacheHit Event Class</span></span>](sp-cachehit-event-class.md)|<span data-ttu-id="5f14e-118">Indica la presenza della stored procedure nella cache.</span><span class="sxs-lookup"><span data-stu-id="5f14e-118">Indicates that the stored procedure is in the cache.</span></span>|  
|[<span data-ttu-id="5f14e-119">Classe di evento SP:CacheInsert</span><span class="sxs-lookup"><span data-stu-id="5f14e-119">SP:CacheInsert Event Class</span></span>](sp-cacheinsert-event-class.md)|<span data-ttu-id="5f14e-120">Indica l'inserimento della stored procedure nella cache.</span><span class="sxs-lookup"><span data-stu-id="5f14e-120">Indicates that the stored procedure has been brought into the cache.</span></span>|  
|[<span data-ttu-id="5f14e-121">Classe di evento SP:CacheMiss</span><span class="sxs-lookup"><span data-stu-id="5f14e-121">SP:CacheMiss Event Class</span></span>](sp-cachemiss-event-class.md)|<span data-ttu-id="5f14e-122">Indica l'assenza della stored procedure nella cache.</span><span class="sxs-lookup"><span data-stu-id="5f14e-122">Indicates that the stored procedure was not found in the cache.</span></span>|  
|[<span data-ttu-id="5f14e-123">Classe di evento SP:CacheRemove</span><span class="sxs-lookup"><span data-stu-id="5f14e-123">SP:CacheRemove Event Class</span></span>](sp-cacheremove-event-class.md)|<span data-ttu-id="5f14e-124">Indica l'eliminazione della stored procedure dalla cache.</span><span class="sxs-lookup"><span data-stu-id="5f14e-124">Indicates that the stored procedure has been removed from the cache.</span></span>|  
|[<span data-ttu-id="5f14e-125">Classe di evento SP:Completed</span><span class="sxs-lookup"><span data-stu-id="5f14e-125">SP:Completed Event Class</span></span>](sp-completed-event-class.md)|<span data-ttu-id="5f14e-126">Indica il completamento dell'esecuzione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5f14e-126">Indicates that execution of the stored procedure has completed.</span></span>|  
|[<span data-ttu-id="5f14e-127">Classe di evento SP:Recompile</span><span class="sxs-lookup"><span data-stu-id="5f14e-127">SP:Recompile Event Class</span></span>](sp-recompile-event-class.md)|<span data-ttu-id="5f14e-128">Indica la ricompilazione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5f14e-128">Indicates that the stored procedure has been recompiled.</span></span>|  
|[<span data-ttu-id="5f14e-129">Classe di evento SP:Starting</span><span class="sxs-lookup"><span data-stu-id="5f14e-129">SP:Starting Event Class</span></span>](sp-starting-event-class.md)|<span data-ttu-id="5f14e-130">Indica l'avvio dell'esecuzione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5f14e-130">Indicates that execution of the stored procedure is starting.</span></span>|  
|[<span data-ttu-id="5f14e-131">Classe di evento SP:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="5f14e-131">SP:StmtCompleted Event Class</span></span>](sp-stmtcompleted-event-class.md)|<span data-ttu-id="5f14e-132">Indica il completamento di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5f14e-132">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has completed.</span></span>|  
|[<span data-ttu-id="5f14e-133">Classe di evento SP:StmtStarting</span><span class="sxs-lookup"><span data-stu-id="5f14e-133">SP:StmtStarting Event Class</span></span>](sp-stmtstarting-event-class.md)|<span data-ttu-id="5f14e-134">Indica l'avvio di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5f14e-134">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f14e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f14e-135">See Also</span></span>  
 <span data-ttu-id="5f14e-136">[Eventi estesi](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="5f14e-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="5f14e-137">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5f14e-137">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
