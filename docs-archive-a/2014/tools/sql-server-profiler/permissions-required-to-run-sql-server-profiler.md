---
title: Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], permissions
- traces [SQL Server], replaying
- replaying traces
- SQL Server Profiler, permissions
- security [SQL Server], SQL Server Profiler
ms.assetid: 5c580a87-88ae-4314-8fe1-54ade83f227f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e73ffe2e127299db9a9e37e48f089aab2cccca52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722083"
---
# <a name="permissions-required-to-run-sql-server-profiler"></a><span data-ttu-id="9f617-102">Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9f617-102">Permissions Required to Run SQL Server Profiler</span></span>
  <span data-ttu-id="9f617-103">Per impostazione predefinita, l'esecuzione di [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] richiede le stesse autorizzazioni utente necessarie per le stored procedure Transact-SQL utilizzate per la creazione di tracce.</span><span class="sxs-lookup"><span data-stu-id="9f617-103">By default, running [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requires the same user permissions as the Transact-SQL stored procedures that are used to create traces.</span></span> <span data-ttu-id="9f617-104">Per eseguire [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], è necessario che agli utenti venga concessa l'autorizzazione ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="9f617-104">To run [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], users must be granted the ALTER TRACE permission.</span></span> <span data-ttu-id="9f617-105">Per altre informazioni, vedere [GRANT - autorizzazioni per server &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9f617-105">For more information, see [GRANT Server Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="9f617-106">Gli utenti che dispongono dell'autorizzazione SHOWPLAN, ALTER TRACE o VIEW SERVER STATE possono visualizzare le query acquisite nell'output di Showplan.</span><span class="sxs-lookup"><span data-stu-id="9f617-106">Users who have the SHOWPLAN, the ALTER TRACE, or the VIEW SERVER STATE permission can view queries that are captured in Showplan output.</span></span> <span data-ttu-id="9f617-107">Poiché tali query possono contenere informazioni riservate, ad esempio password,</span><span class="sxs-lookup"><span data-stu-id="9f617-107">These queries may contain sensitive information such as passwords.</span></span> <span data-ttu-id="9f617-108">è consigliabile concedere tali autorizzazioni solo agli utenti che possono visualizzare le informazioni riservate, ad esempio ai membri del ruolo predefinito del database db_owner oppure ai membri del ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="9f617-108">Therefore, we recommend that you only grant these permissions to users who are authorized to view sensitive information, such as members of the db_owner fixed database role, or members of the sysadmin fixed server role.</span></span> <span data-ttu-id="9f617-109">È inoltre consigliabile salvare file Showplan o file di traccia che contengono eventi correlati a Showplan solo in una posizione che utilizza il file system NTFS e limitare l'accesso agli utenti autorizzati a visualizzare le informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="9f617-109">Additionally, we recommend that you only save Showplan files or trace files that contain Showplan-related events to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view sensitive information.</span></span>

## <a name="permissions-used-to-replay-traces"></a><span data-ttu-id="9f617-110">Autorizzazioni per la riproduzione di tracce</span><span class="sxs-lookup"><span data-stu-id="9f617-110">Permissions Used to Replay Traces</span></span>
 <span data-ttu-id="9f617-111">Per riprodurre le tracce, è necessario che l'utente che desidera eseguire questa operazione disponga dell'autorizzazione ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="9f617-111">Replaying traces also requires that the user who is replaying the trace have the ALTER TRACE permission.</span></span>

 <span data-ttu-id="9f617-112">Durante la riproduzione, in [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] viene tuttavia utilizzato il comando EXECUTE AS, se nella traccia riprodotta viene rilevato un evento Audit Login.</span><span class="sxs-lookup"><span data-stu-id="9f617-112">However, during replay, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] uses the EXECUTE AS command if an Audit Login event is encountered in the trace that is being replayed.</span></span> [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="9f617-113">usa il comando EXECUTE AS per rappresentare l'utente associato all'evento di accesso.</span><span class="sxs-lookup"><span data-stu-id="9f617-113">uses the EXECUTE AS command to impersonate the user who is associated with the login event.</span></span>

 <span data-ttu-id="9f617-114">Se [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] rileva un evento di accesso in una traccia che si desidera riprodurre, verranno eseguite le verifiche delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f617-114">If [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encounters a login event in a trace that is being replayed, the following permission checks are performed:</span></span>

1.  <span data-ttu-id="9f617-115">Utente1, che dispone dell'autorizzazione ALTER TRACE, inizia la riproduzione di una traccia.</span><span class="sxs-lookup"><span data-stu-id="9f617-115">User1, who has the ALTER TRACE permission, starts replaying a trace.</span></span>

2.  <span data-ttu-id="9f617-116">Nella traccia riprodotta viene rilevato un evento di accesso per Utente2.</span><span class="sxs-lookup"><span data-stu-id="9f617-116">A login event for User2 is encountered in the replayed trace.</span></span>

3.  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="9f617-117">usa il comando EXECUTE AS per rappresentare Utente2.</span><span class="sxs-lookup"><span data-stu-id="9f617-117">uses the EXECUTE AS command to impersonate User2.</span></span>

4.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9f617-118">prova a eseguire l'autenticazione di Utente2 e, in base ai risultati, si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f617-118">attempts to authenticate User2, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="9f617-119">Se non è possibile eseguire l'autenticazione di Utente2, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] restituisce un errore e continua la riproduzione della traccia come Utente1.</span><span class="sxs-lookup"><span data-stu-id="9f617-119">If User2 cannot be authenticated, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] returns an error, and continues replaying the trace as User1.</span></span>

    2.  <span data-ttu-id="9f617-120">Se l'autenticazione di Utente2 viene eseguita, la riproduzione della traccia continua come Utente2.</span><span class="sxs-lookup"><span data-stu-id="9f617-120">If User2 is successfully authenticated, replaying the trace as User2 continues.</span></span>

5.  <span data-ttu-id="9f617-121">Vengono controllate le autorizzazioni di Utente2 nel database di destinazione e, in base ai risultati, si può verificare una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f617-121">Permissions for User2 are checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="9f617-122">Se Utente2 dispone delle autorizzazioni per il database di destinazione, la rappresentazione ha esito positivo e la riproduzione della traccia viene eseguita come Utente2.</span><span class="sxs-lookup"><span data-stu-id="9f617-122">If User2 has permissions on the target database, impersonation has succeeded, and the trace is replayed as User2.</span></span>

    2.  <span data-ttu-id="9f617-123">Se Utente2 non dispone delle autorizzazioni per il database di destinazione, il server verifica se esiste un utente Guest nel database.</span><span class="sxs-lookup"><span data-stu-id="9f617-123">If User2 does not have permissions on the target database, the server checks for a Guest user on that database.</span></span>

6.  <span data-ttu-id="9f617-124">Viene verificata l'esistenza di un utente Guest nel database di destinazione e, in base ai risultati, si può verificare una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f617-124">Existence of a Guest user is checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="9f617-125">Se esiste un account Guest, la riproduzione della traccia viene eseguita come account Guest.</span><span class="sxs-lookup"><span data-stu-id="9f617-125">If a Guest account exists, the trace is replayed as the Guest account.</span></span>

    2.  <span data-ttu-id="9f617-126">Se nel database di destinazione non esiste un account Guest, viene restituito un errore e la riproduzione della traccia viene eseguita come Utente1.</span><span class="sxs-lookup"><span data-stu-id="9f617-126">If no Guest account exists on the target database, an error is returned and the trace is replayed as User1.</span></span>

 <span data-ttu-id="9f617-127">Nella figura seguente viene illustrato il processo di verifica delle autorizzazioni per la riproduzione delle tracce:</span><span class="sxs-lookup"><span data-stu-id="9f617-127">The following diagram shows this process of checking permission when replaying traces:</span></span>

 <span data-ttu-id="9f617-128">![Autorizzazioni per la riproduzione di tracce di SQL Server Profiler](../../database-engine/media/replaytracedecisiontree.gif "Autorizzazioni per la riproduzione di tracce di SQL Server Profiler")</span><span class="sxs-lookup"><span data-stu-id="9f617-128">![SQL Server Profiler replay trace permissions](../../database-engine/media/replaytracedecisiontree.gif "SQL Server Profiler replay trace permissions")</span></span>

## <a name="see-also"></a><span data-ttu-id="9f617-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f617-129">See Also</span></span>
 <span data-ttu-id="9f617-130">[SQL Server Profiler stored procedure &#40;Transact-SQL&#41;riproduzione delle](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [tracce](replay-traces.md) [creare una traccia &#40;SQL Server Profiler](create-a-trace-sql-server-profiler.md)&#41;[riprodurre una tabella di traccia &#40;](replay-a-trace-table-sql-server-profiler.md) SQL Server Profiler&#41;[riprodurre un file di traccia](replay-a-trace-file-sql-server-profiler.md) &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="9f617-130">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay Traces](replay-traces.md) [Create a Trace &#40;SQL Server Profiler&#41;](create-a-trace-sql-server-profiler.md) [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md)</span></span>


