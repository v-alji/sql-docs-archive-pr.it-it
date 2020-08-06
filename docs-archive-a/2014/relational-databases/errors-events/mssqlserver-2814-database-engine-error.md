---
title: MSSQLSERVER_2814 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2814 (Database Engine error)
ms.assetid: 22800748-9be9-4511-9428-6b8b40e5bef9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26b1fae5b683ed72cb93c3f81981bd41e2f4ad4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628745"
---
# <a name="mssqlserver_2814"></a><span data-ttu-id="a3555-102">MSSQLSERVER_2814</span><span class="sxs-lookup"><span data-stu-id="a3555-102">MSSQLSERVER_2814</span></span>
    
## <a name="details"></a><span data-ttu-id="a3555-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a3555-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3555-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a3555-104">Product Name</span></span>|<span data-ttu-id="a3555-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3555-105">SQL Server</span></span>|  
|<span data-ttu-id="a3555-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a3555-106">Event ID</span></span>|<span data-ttu-id="a3555-107">2814</span><span class="sxs-lookup"><span data-stu-id="a3555-107">2814</span></span>|  
|<span data-ttu-id="a3555-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a3555-108">Event Source</span></span>|<span data-ttu-id="a3555-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3555-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3555-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3555-110">Component</span></span>|<span data-ttu-id="a3555-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a3555-111">SQLEngine</span></span>|  
|<span data-ttu-id="a3555-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a3555-112">Symbolic Name</span></span>|<span data-ttu-id="a3555-113">PR_POSSIBLE_INFINITE_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="a3555-113">PR_POSSIBLE_INFINITE_RECOMPILE</span></span>|  
|<span data-ttu-id="a3555-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a3555-114">Message Text</span></span>|<span data-ttu-id="a3555-115">Rilevata una possibile ricompilazione infinita per SQLHANDLE %hs, PlanHandle %hs, offset iniziale %d, offset finale %d.</span><span class="sxs-lookup"><span data-stu-id="a3555-115">A possible infinite recompile was detected for SQLHANDLE %hs, PlanHandle %hs, starting offset %d, ending offset %d.</span></span> <span data-ttu-id="a3555-116">Motivo dell'ultima ricompilazione: % d.</span><span class="sxs-lookup"><span data-stu-id="a3555-116">The last recompile reason was %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3555-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a3555-117">Explanation</span></span>  
 <span data-ttu-id="a3555-118">Una o più istruzioni ha determinato la ricompilazione del batch di query almeno 50 volte.</span><span class="sxs-lookup"><span data-stu-id="a3555-118">One or more statements caused the query batch to recompile at least 50 times.</span></span> <span data-ttu-id="a3555-119">Per evitare ulteriori ricompilazioni, è necessario correggere l'istruzione specificata.</span><span class="sxs-lookup"><span data-stu-id="a3555-119">The specified statement should be corrected to avoid further recompilations.</span></span>  
  
 <span data-ttu-id="a3555-120">I motivi della ricompilazione sono elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a3555-120">The following table lists the reasons for recompilation.</span></span>  
  
|<span data-ttu-id="a3555-121">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="a3555-121">Reason code</span></span>|<span data-ttu-id="a3555-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3555-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a3555-123">1</span><span class="sxs-lookup"><span data-stu-id="a3555-123">1</span></span>|<span data-ttu-id="a3555-124">Schema modificato</span><span class="sxs-lookup"><span data-stu-id="a3555-124">Schema changed</span></span>|  
|<span data-ttu-id="a3555-125">2</span><span class="sxs-lookup"><span data-stu-id="a3555-125">2</span></span>|<span data-ttu-id="a3555-126">Statistiche modificate</span><span class="sxs-lookup"><span data-stu-id="a3555-126">Statistics changed</span></span>|  
|<span data-ttu-id="a3555-127">3</span><span class="sxs-lookup"><span data-stu-id="a3555-127">3</span></span>|<span data-ttu-id="a3555-128">Compilazione posticipata</span><span class="sxs-lookup"><span data-stu-id="a3555-128">Deferred compile</span></span>|  
|<span data-ttu-id="a3555-129">4</span><span class="sxs-lookup"><span data-stu-id="a3555-129">4</span></span>|<span data-ttu-id="a3555-130">Opzione impostata modificata</span><span class="sxs-lookup"><span data-stu-id="a3555-130">Set option changed</span></span>|  
|<span data-ttu-id="a3555-131">5</span><span class="sxs-lookup"><span data-stu-id="a3555-131">5</span></span>|<span data-ttu-id="a3555-132">Tabella temporanea modificata</span><span class="sxs-lookup"><span data-stu-id="a3555-132">Temp table changed</span></span>|  
|<span data-ttu-id="a3555-133">6</span><span class="sxs-lookup"><span data-stu-id="a3555-133">6</span></span>|<span data-ttu-id="a3555-134">Set di righe remoto modificato</span><span class="sxs-lookup"><span data-stu-id="a3555-134">Remote rowset changed</span></span>|  
|<span data-ttu-id="a3555-135">7</span><span class="sxs-lookup"><span data-stu-id="a3555-135">7</span></span>|<span data-ttu-id="a3555-136">Autorizzazioni FOR BROWSE modificate</span><span class="sxs-lookup"><span data-stu-id="a3555-136">For Browse permissions changed</span></span>|  
|<span data-ttu-id="a3555-137">8</span><span class="sxs-lookup"><span data-stu-id="a3555-137">8</span></span>|<span data-ttu-id="a3555-138">Ambiente di notifica query modificato</span><span class="sxs-lookup"><span data-stu-id="a3555-138">Query notification environment changed</span></span>|  
|<span data-ttu-id="a3555-139">9</span><span class="sxs-lookup"><span data-stu-id="a3555-139">9</span></span>|<span data-ttu-id="a3555-140">Vista partizionata modificata</span><span class="sxs-lookup"><span data-stu-id="a3555-140">Partition view changed</span></span>|  
|<span data-ttu-id="a3555-141">10</span><span class="sxs-lookup"><span data-stu-id="a3555-141">10</span></span>|<span data-ttu-id="a3555-142">Opzioni cursore modificate</span><span class="sxs-lookup"><span data-stu-id="a3555-142">Cursor options changed</span></span>|  
|<span data-ttu-id="a3555-143">11</span><span class="sxs-lookup"><span data-stu-id="a3555-143">11</span></span>|<span data-ttu-id="a3555-144">Opzione (recompile) richiesta</span><span class="sxs-lookup"><span data-stu-id="a3555-144">Option (recompile) requested</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="a3555-145">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a3555-145">User Action</span></span>  
  
1.  <span data-ttu-id="a3555-146">Visualizzare l'istruzione che determina la ricompilazione mediante l'esecuzione della query seguente.</span><span class="sxs-lookup"><span data-stu-id="a3555-146">View the statement causing the recompilation by running the following query.</span></span> <span data-ttu-id="a3555-147">Sostituire i segnaposto *sql_handle*, *starting_offset*, *ending_offset* e *plan_handle* con i valori specificati nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="a3555-147">Replace the *sql_handle*, *starting_offset*, *ending_offset*, and *plan_handle* placeholders with the values specified in the error message.</span></span> <span data-ttu-id="a3555-148">Notare che le colonne **database_name** e **object_name** saranno NULL per le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc e preparate.</span><span class="sxs-lookup"><span data-stu-id="a3555-148">Note that the **database_name** and **object_name** columns will be NULL for ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="a3555-149">SELECT DB_NAME(st.dbid) AS database_name</span><span class="sxs-lookup"><span data-stu-id="a3555-149">SELECT DB_NAME(st.dbid) AS database_name</span></span>  
  
     <span data-ttu-id="a3555-150">, OBJECT_NAME(st.objectid) AS object_name</span><span class="sxs-lookup"><span data-stu-id="a3555-150">, OBJECT_NAME(st.objectid) AS object_name</span></span>  
  
     <span data-ttu-id="a3555-151">, st.text</span><span class="sxs-lookup"><span data-stu-id="a3555-151">, st.text</span></span>  
  
     <span data-ttu-id="a3555-152">FROM sys.dm_exec_query_stats AS qs</span><span class="sxs-lookup"><span data-stu-id="a3555-152">FROM sys.dm_exec_query_stats AS qs</span></span>  
  
     <span data-ttu-id="a3555-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span><span class="sxs-lookup"><span data-stu-id="a3555-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span></span>  
  
     <span data-ttu-id="a3555-154">WHERE qs.statement_start_offset = *starting_offset*</span><span class="sxs-lookup"><span data-stu-id="a3555-154">WHERE qs.statement_start_offset = *starting_offset*</span></span>  
  
     <span data-ttu-id="a3555-155">AND qs.statement_end_offset = *ending_offset*</span><span class="sxs-lookup"><span data-stu-id="a3555-155">AND qs.statement_end_offset = *ending_offset*</span></span>  
  
     <span data-ttu-id="a3555-156">AND qs.plan_handle = *plan_handle*;</span><span class="sxs-lookup"><span data-stu-id="a3555-156">AND qs.plan_handle = *plan_handle*;</span></span>  
  
2.  <span data-ttu-id="a3555-157">In base alla descrizione del codice motivo, modificare l'istruzione, il batch o la procedura per evitare ricompilazioni.</span><span class="sxs-lookup"><span data-stu-id="a3555-157">Based on the reason code description, modify the statement, batch, or procedure to avoid recompilations.</span></span> <span data-ttu-id="a3555-158">Una stored procedure può contenere, ad esempio, uno o più istruzioni SET.</span><span class="sxs-lookup"><span data-stu-id="a3555-158">For example, a stored procedure may contain one or more SET statements.</span></span> <span data-ttu-id="a3555-159">Queste istruzioni devono essere rimosse dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="a3555-159">These statements should be removed from the procedure.</span></span> <span data-ttu-id="a3555-160">Per esempi aggiuntivi sulle cause e sulle risoluzioni dei problemi di ricompilazione, vedere [Problematiche di compilazione batch, ricompilazione e memorizzazione dei piani nella cache in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="a3555-160">For additional examples of recompilation causes and resolutions, see [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span></span>  
  
3.  <span data-ttu-id="a3555-161">Se il problema persiste, contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3555-161">If the problem persists, contact Microsoft Customer Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3555-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3555-162">See Also</span></span>  
 [<span data-ttu-id="a3555-163">Classe di evento SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="a3555-163">SQL:StmtRecompile Event Class</span></span>](../event-classes/sql-stmtrecompile-event-class.md)  
  
  
