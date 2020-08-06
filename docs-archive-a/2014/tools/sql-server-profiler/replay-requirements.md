---
title: Requisiti per la riproduzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event classes [SQL Server], replaying traces
- traces [SQL Server], replaying
- replaying traces
- TSQL_Replay template [SQL Server]
ms.assetid: 0e01dfc7-84b9-47f6-8bf7-b0656df4fa7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65546f6820765286b558d2043e0155a79a07eb58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722055"
---
# <a name="replay-requirements"></a><span data-ttu-id="72998-102">Requisiti per la riproduzione</span><span class="sxs-lookup"><span data-stu-id="72998-102">Replay Requirements</span></span>
  <span data-ttu-id="72998-103">Per riprodurre dati di traccia con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o Distributed Replay Utility, è necessario acquisire un set specifico di classi di evento e colonne nella traccia.</span><span class="sxs-lookup"><span data-stu-id="72998-103">In order to replay trace data with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or the Distributed Replay Utility, a specific set of event classes and columns must be captured in the trace.</span></span> <span data-ttu-id="72998-104">Queste impostazioni sono abilitate per impostazione predefinita se si usa il modello di traccia **TSQL_Replay** per configurare una traccia usata successivamente per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="72998-104">These settings are enabled by default if the **TSQL_Replay** trace template is used to configure a trace that is later used for replay.</span></span> <span data-ttu-id="72998-105">In questo argomento vengono descritte queste impostazioni e altri requisiti per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="72998-105">This topic describes these settings and other replay requirements.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72998-106">È consigliabile utilizzare Distributed Replay Utility per riprodurre un'applicazione OLTP intensiva (con molte connessioni simultanee attive o una velocità effettiva elevata).</span><span class="sxs-lookup"><span data-stu-id="72998-106">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="72998-107">Distributed Replay Utility può riprodurre dati di traccia da più computer, per simulare in modo migliore un carico di lavoro di importanza critica.</span><span class="sxs-lookup"><span data-stu-id="72998-107">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="72998-108">Per altre informazioni, vedere [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="72998-108">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="event-classes-required-for-replay"></a><span data-ttu-id="72998-109">Classi di evento necessarie per la riproduzione</span><span class="sxs-lookup"><span data-stu-id="72998-109">Event Classes Required for Replay</span></span>  
 <span data-ttu-id="72998-110">Ai fini della riproduzione tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], è necessario acquisire nella traccia il set di classi di evento seguente, oltre ad altre classi di evento che si desidera monitorare:</span><span class="sxs-lookup"><span data-stu-id="72998-110">To be replayed by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], the following set of event classes, in addition to any other event classes you want to monitor, must be captured in the trace:</span></span>  
  
-   <span data-ttu-id="72998-111">**CursorClose (** necessaria solo per la riproduzione di cursori sul lato server)</span><span class="sxs-lookup"><span data-stu-id="72998-111">**CursorClose (** only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="72998-112">**CursorExecute (** necessaria solo per la riproduzione di cursori sul lato server)</span><span class="sxs-lookup"><span data-stu-id="72998-112">**CursorExecute** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="72998-113">**CursorOpen (** necessaria solo per la riproduzione di cursori sul lato server)</span><span class="sxs-lookup"><span data-stu-id="72998-113">**CursorOpen** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="72998-114">**CursorPrepare (** necessaria solo per la riproduzione di cursori sul lato server)</span><span class="sxs-lookup"><span data-stu-id="72998-114">**CursorPrepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="72998-115">**CursorUnprepare (** necessaria solo per la riproduzione di cursori sul lato server)</span><span class="sxs-lookup"><span data-stu-id="72998-115">**CursorUnprepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="72998-116">**Audit Login**</span><span class="sxs-lookup"><span data-stu-id="72998-116">**Audit Login**</span></span>  
  
-   <span data-ttu-id="72998-117">**Audit Logout**</span><span class="sxs-lookup"><span data-stu-id="72998-117">**Audit Logout**</span></span>  
  
-   <span data-ttu-id="72998-118">**ExistingConnection**</span><span class="sxs-lookup"><span data-stu-id="72998-118">**ExistingConnection**</span></span>  
  
-   <span data-ttu-id="72998-119">**RPC Output Parameter**</span><span class="sxs-lookup"><span data-stu-id="72998-119">**RPC Output Parameter**</span></span>  
  
-   <span data-ttu-id="72998-120">**RPC:Completed**</span><span class="sxs-lookup"><span data-stu-id="72998-120">**RPC:Completed**</span></span>  
  
-   <span data-ttu-id="72998-121">**RPC:Starting**</span><span class="sxs-lookup"><span data-stu-id="72998-121">**RPC:Starting**</span></span>  
  
-   <span data-ttu-id="72998-122">**Exec Prepared SQL** (necessaria solo per la riproduzione di istruzioni SQL preparate sul lato server)</span><span class="sxs-lookup"><span data-stu-id="72998-122">**Exec Prepared SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="72998-123">**Prepare SQL** (necessaria solo per la riproduzione di istruzioni SQL preparate sul lato server)</span><span class="sxs-lookup"><span data-stu-id="72998-123">**Prepare SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="72998-124">**SQL:BatchCompleted**</span><span class="sxs-lookup"><span data-stu-id="72998-124">**SQL:BatchCompleted**</span></span>  
  
-   <span data-ttu-id="72998-125">**SQL:BatchStarting**</span><span class="sxs-lookup"><span data-stu-id="72998-125">**SQL:BatchStarting**</span></span>  
  
## <a name="data-columns-required-for-replay"></a><span data-ttu-id="72998-126">Colonne di dati necessarie per la riproduzione</span><span class="sxs-lookup"><span data-stu-id="72998-126">Data Columns Required for Replay</span></span>  
 <span data-ttu-id="72998-127">Per consentire la riproduzione di una traccia, è necessario acquisire le colonne di dati seguenti, insieme alle colonne di dati che si desidera monitorare:</span><span class="sxs-lookup"><span data-stu-id="72998-127">In addition to any other data columns you want to capture, the following data columns must be captured in a trace to allow the trace to be replayed:</span></span>  
  
-   <span data-ttu-id="72998-128">**Event Class**</span><span class="sxs-lookup"><span data-stu-id="72998-128">**Event Class**</span></span>  
  
-   <span data-ttu-id="72998-129">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="72998-129">**EventSequence**</span></span>  
  
-   <span data-ttu-id="72998-130">**TextData**</span><span class="sxs-lookup"><span data-stu-id="72998-130">**TextData**</span></span>  
  
-   <span data-ttu-id="72998-131">**Nome dell'applicazione**</span><span class="sxs-lookup"><span data-stu-id="72998-131">**Application Name**</span></span>  
  
-   <span data-ttu-id="72998-132">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="72998-132">**LoginName**</span></span>  
  
-   <span data-ttu-id="72998-133">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="72998-133">**DatabaseName**</span></span>  
  
-   <span data-ttu-id="72998-134">**ID database**</span><span class="sxs-lookup"><span data-stu-id="72998-134">**Database ID**</span></span>  
  
-   <span data-ttu-id="72998-135">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="72998-135">**ClientProcessID**</span></span>  
  
-   <span data-ttu-id="72998-136">**HostName**</span><span class="sxs-lookup"><span data-stu-id="72998-136">**HostName**</span></span>  
  
-   <span data-ttu-id="72998-137">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="72998-137">**ServerName**</span></span>  
  
-   <span data-ttu-id="72998-138">**Binary Data**</span><span class="sxs-lookup"><span data-stu-id="72998-138">**Binary Data**</span></span>  
  
-   <span data-ttu-id="72998-139">**SPID**</span><span class="sxs-lookup"><span data-stu-id="72998-139">**SPID**</span></span>  
  
-   <span data-ttu-id="72998-140">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="72998-140">**Start Time**</span></span>  
  
-   <span data-ttu-id="72998-141">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="72998-141">**EndTime**</span></span>  
  
-   <span data-ttu-id="72998-142">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="72998-142">**IsSystem**</span></span>  
  
-   <span data-ttu-id="72998-143">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="72998-143">**NTDomainName**</span></span>  
  
-   <span data-ttu-id="72998-144">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="72998-144">**NTUserName**</span></span>  
  
-   <span data-ttu-id="72998-145">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="72998-145">**Error**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72998-146">Usare il modello di traccia **TSQL_Replay** per le tracce che consentono di acquisire i dati per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="72998-146">Use the trace template **TSQL_Replay** for traces that capture data for replay.</span></span>  
  
## <a name="other-replay-requirements"></a><span data-ttu-id="72998-147">Altri requisiti per la riproduzione</span><span class="sxs-lookup"><span data-stu-id="72998-147">Other Replay Requirements</span></span>  
 <span data-ttu-id="72998-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]durante la riproduzione viene verificata la presenza delle colonne e degli eventi necessari.</span><span class="sxs-lookup"><span data-stu-id="72998-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], replay checks for the presence of required events and columns.</span></span> <span data-ttu-id="72998-149">Questa modifica contribuisce a migliorare la precisione della riproduzione e a rendere più specifica la risoluzione dei problemi di riproduzione in caso di mancanza di dati necessari.</span><span class="sxs-lookup"><span data-stu-id="72998-149">This change helps improve the accuracy of replay and takes the guesswork out of troubleshooting replay when required data is missing.</span></span> <span data-ttu-id="72998-150">Se i dati necessari non sono disponibili in una traccia, viene restituito un errore di riproduzione e la riproduzione del file viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="72998-150">Replay returns an error and stops replaying a file when required data is missing from a trace.</span></span>  
  
 <span data-ttu-id="72998-151">Per riprodurre una traccia in un server (destinazione) in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione, diverso dal server in cui la traccia veniva eseguita originariamente (origine), assicurarsi che siano state eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="72998-151">To replay a trace against a server (the target) on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running other than the server originally traced (the source), make sure the following has been done:</span></span>  
  
-   <span data-ttu-id="72998-152">È necessario che tutti gli account di accesso e gli utenti inclusi nella traccia siano disponibili nella destinazione e nello stesso database dell'origine.</span><span class="sxs-lookup"><span data-stu-id="72998-152">All logins and users contained in the trace must be created already on the target and in the same database as the source.</span></span>  
  
-   <span data-ttu-id="72998-153">È necessario che tutti gli account di accesso e gli utenti nella destinazione dispongano delle stesse autorizzazioni disponibili nell'origine.</span><span class="sxs-lookup"><span data-stu-id="72998-153">All logins and users in the target must have the same permissions they had in the source.</span></span>  
  
-   <span data-ttu-id="72998-154">Tutte le password di accesso devono essere uguali a quella dell'utente che esegue la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="72998-154">All login passwords must be the same as those of the user that executes the replay.</span></span>  
  
-   <span data-ttu-id="72998-155">È consigliabile che gli ID di database nella destinazione e nell'origine siano uguali.</span><span class="sxs-lookup"><span data-stu-id="72998-155">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="72998-156">In caso contrario, tuttavia, è possibile trovare una corrispondenza in base a **DatabaseName** , se presente nella traccia.</span><span class="sxs-lookup"><span data-stu-id="72998-156">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="72998-157">È necessario che il database predefinito per ogni account di accesso incluso nella traccia sia impostato (nella destinazione) sul database di destinazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="72998-157">The default database for each login contained in the trace must be set (on the target) to the respective target database of the login.</span></span> <span data-ttu-id="72998-158">Si supponga ad esempio che la traccia da riprodurre includa attività per l'account di accesso **Fred**nel database **Fred_Db** nell'origine.</span><span class="sxs-lookup"><span data-stu-id="72998-158">For example, the trace to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the source.</span></span> <span data-ttu-id="72998-159">Quindi nella destinazione il database predefinito per l'account **Fred**deve essere impostato sul database corrispondente a **Fred_Db** , anche se il nome del database è diverso.</span><span class="sxs-lookup"><span data-stu-id="72998-159">Therefore, on the target, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="72998-160">Per impostare il database predefinito dell'account di accesso, usare la stored procedure di sistema **sp_defaultdb** .</span><span class="sxs-lookup"><span data-stu-id="72998-160">To set the default database of the login, use the **sp_defaultdb** system stored procedure.</span></span>  
  
 <span data-ttu-id="72998-161">La riproduzione degli eventi associati ad account di accesso mancanti o non corretti genera errori di riproduzione, ma l'operazione non viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="72998-161">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
 <span data-ttu-id="72998-162">Per informazioni sulle autorizzazioni necessarie per riprodurre una traccia, vedere [Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="72998-162">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72998-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72998-163">See Also</span></span>  
 <span data-ttu-id="72998-164">[Riprodurre una tabella di traccia &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="72998-164">[Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="72998-165">[Riprodurre un file di traccia &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="72998-165">[Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="72998-166">[Guida di riferimento alle classi di evento SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="72998-166">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="72998-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="72998-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span></span>  
 [<span data-ttu-id="72998-168">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="72998-168">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
