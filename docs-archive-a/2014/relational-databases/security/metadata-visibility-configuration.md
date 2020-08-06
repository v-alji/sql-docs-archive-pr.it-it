---
title: Configurazione della visibilità dei metadati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- subcomponents visibility [SQL Server]
- metadata [SQL Server], visibility
- permissions [SQL Server], metadata access
- viewing metadata
- objects [SQL Server], metadata
- displaying metadata
- database metadata [SQL Server]
- metadata [SQL Server], permissions
ms.assetid: 50d2e015-05ae-4014-a1cd-4de7866ad651
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5198dc4ba4e81bc1d7a8dd2411da59da81596102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629313"
---
# <a name="metadata-visibility-configuration"></a><span data-ttu-id="c0558-102">Configurazione della visibilità dei metadati</span><span class="sxs-lookup"><span data-stu-id="c0558-102">Metadata Visibility Configuration</span></span>
  <span data-ttu-id="c0558-103">La visibilità dei metadati è limitata alle entità a protezione diretta di cui l'utente è proprietario o per le quali dispone di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c0558-103">The visibility of metadata is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="c0558-104">Ad esempio, la query seguente restituisce una riga se all'utente è stata concessa un'autorizzazione SELECT o INSERT per la tabella `myTable`.</span><span class="sxs-lookup"><span data-stu-id="c0558-104">For example, the following query returns a row if the user has been granted a permission such as SELECT or INSERT on the table `myTable`.</span></span>  
  
```  
SELECT name, object_id  
FROM sys.tables  
WHERE name = 'myTable';  
GO  
```  
  
 <span data-ttu-id="c0558-105">Se invece l'utente non dispone di alcuna autorizzazione per `myTable`, la query restituisce un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="c0558-105">However, if the user does not have any permission on `myTable`, the query returns an empty result set.</span></span>  
  
## <a name="scope-and-impact-of-metadata-visibility-configuration"></a><span data-ttu-id="c0558-106">Ambito e impatto della configurazione della visibilità dei metadati</span><span class="sxs-lookup"><span data-stu-id="c0558-106">Scope and Impact of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="c0558-107">È possibile configurare la visibilità dei metadati unicamente per le entità a protezione diretta seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0558-107">Metadata visibility configuration only applies to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0558-108">Viste del catalogo</span><span class="sxs-lookup"><span data-stu-id="c0558-108">Catalog views</span></span>|<span data-ttu-id="c0558-109">Stored procedure **sp_help** del [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0558-109">[!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures</span></span>|  
|<span data-ttu-id="c0558-110">Metadati che espongono funzioni predefinite</span><span class="sxs-lookup"><span data-stu-id="c0558-110">Metadata exposing built-in functions</span></span>|<span data-ttu-id="c0558-111">Viste degli schemi delle informazioni</span><span class="sxs-lookup"><span data-stu-id="c0558-111">Information schema views</span></span>|  
|<span data-ttu-id="c0558-112">Viste di compatibilità</span><span class="sxs-lookup"><span data-stu-id="c0558-112">Compatibility views</span></span>|<span data-ttu-id="c0558-113">Proprietà estese</span><span class="sxs-lookup"><span data-stu-id="c0558-113">Extended properties</span></span>|  
  
 <span data-ttu-id="c0558-114">Non è possibile configurare la visibilità dei metadati per le entità a protezione diretta seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0558-114">Metadata visibility configuration does not apply to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0558-115">Tabelle di sistema per il log shipping</span><span class="sxs-lookup"><span data-stu-id="c0558-115">Log shipping system tables</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0558-116">Tabelle di sistema dell'agente</span><span class="sxs-lookup"><span data-stu-id="c0558-116">Agent system tables</span></span>|  
|<span data-ttu-id="c0558-117">Tabelle di sistema del piano di manutenzione database</span><span class="sxs-lookup"><span data-stu-id="c0558-117">Database maintenance plan system tables</span></span>|<span data-ttu-id="c0558-118">Tabelle di sistema di backup</span><span class="sxs-lookup"><span data-stu-id="c0558-118">Backup system tables</span></span>|  
|<span data-ttu-id="c0558-119">Tabelle di sistema di replica</span><span class="sxs-lookup"><span data-stu-id="c0558-119">Replication system tables</span></span>|<span data-ttu-id="c0558-120">Replica e stored procedure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sp_help **dell'agente**</span><span class="sxs-lookup"><span data-stu-id="c0558-120">Replication and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **sp_help** stored procedures</span></span>|  
  
 <span data-ttu-id="c0558-121">Un'accessibilità limitata ai metadati comporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c0558-121">Limited metadata accessibility means the following:</span></span>  
  
-   <span data-ttu-id="c0558-122">Le applicazioni per cui è impostato l'accesso **pubblico** ai metadati verranno interrotte.</span><span class="sxs-lookup"><span data-stu-id="c0558-122">Applications that assume **public** metadata access will break.</span></span>  
  
-   <span data-ttu-id="c0558-123">È possibile che le query eseguite su viste di sistema restituiscano solo un subset di righe o a volte un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="c0558-123">Queries on system views might only return a subset of rows, or sometimes an empty result set.</span></span>  
  
-   <span data-ttu-id="c0558-124">È possibile che le funzioni predefinite per la creazione di metadati quali OBJECTPROPERTYEX restituiscano NULL.</span><span class="sxs-lookup"><span data-stu-id="c0558-124">Metadata-emitting, built-in functions such as OBJECTPROPERTYEX may return NULL.</span></span>  
  
-   <span data-ttu-id="c0558-125">È possibile che le stored procedure **sp_help** del [!INCLUDE[ssDE](../../includes/ssde-md.md)] restituiscano solo un subset di righe o NULL.</span><span class="sxs-lookup"><span data-stu-id="c0558-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures might return only a subset of rows, or NULL.</span></span>  
  
 <span data-ttu-id="c0558-126">I moduli SQL, ad esempio le stored procedure e i trigger, vengono eseguiti nel contesto di sicurezza del chiamante e pertanto la relativa accessibilità ai metadati è limitata.</span><span class="sxs-lookup"><span data-stu-id="c0558-126">SQL modules, such as stored procedures and triggers, run under the security context of the caller and, therefore, have limited metadata accessibility.</span></span> <span data-ttu-id="c0558-127">Nel codice di esempio seguente, quando la stored procedure tenta di accedere ai metadati relativi alla tabella `myTable` per la quale il chiamante non dispone di alcun diritto, viene restituito un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="c0558-127">For example, in the following code, when the stored procedure tries to access metadata for the table `myTable` on which the caller has no rights, an empty result set is returned.</span></span> <span data-ttu-id="c0558-128">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], viene invece restituita una riga.</span><span class="sxs-lookup"><span data-stu-id="c0558-128">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a row is returned.</span></span>  
  
```  
CREATE PROCEDURE assumes_caller_can_access_metadata  
BEGIN  
SELECT name, id   
FROM sysobjects   
WHERE name = 'myTable';  
END;  
GO  
```  
  
 <span data-ttu-id="c0558-129">Per consentire ai chiamanti di visualizzare i metadati, è possibile concedere loro l'autorizzazione VIEW DEFINITION in un ambito appropriato, che può essere a livello di oggetto, di database o di server.</span><span class="sxs-lookup"><span data-stu-id="c0558-129">To allow callers to view metadata, you can grant the callers VIEW DEFINITION permission at an appropriate scope: object level, database level or server level.</span></span> <span data-ttu-id="c0558-130">Nell'esempio precedente, se il chiamante dispone dell'autorizzazione VIEW DEFINITION per `myTable`, la stored procedure restituisce pertanto una riga.</span><span class="sxs-lookup"><span data-stu-id="c0558-130">Therefore, in the previous example, if the caller has VIEW DEFINITION permission on `myTable`, the stored procedure returns a row.</span></span> <span data-ttu-id="c0558-131">Per altre informazioni, vedere [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) e [Autorizzazioni di database GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0558-131">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="c0558-132">È inoltre possibile modificare la stored procedure in modo che venga eseguita con le credenziali del proprietario.</span><span class="sxs-lookup"><span data-stu-id="c0558-132">You can also modify the stored procedure so that it executes under the credentials of the owner.</span></span> <span data-ttu-id="c0558-133">Se il proprietario della stored procedure è anche proprietario della tabella, verrà applicata la concatenazione della proprietà e il contesto di sicurezza del proprietario della procedura consentirà di accedere ai metadati relativi a `myTable`.</span><span class="sxs-lookup"><span data-stu-id="c0558-133">When the procedure owner and the table owner are the same owner, ownership chaining applies, and the security context of the procedure owner enables access to the metadata for `myTable`.</span></span> <span data-ttu-id="c0558-134">In questo scenario, il codice seguente restituisce una riga di metadati al chiamante.</span><span class="sxs-lookup"><span data-stu-id="c0558-134">Under this scenario, the following code returns a row of metadata to the caller.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0558-135">Nell'esempio seguente viene usata la vista del catalogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) anziché la vista di compatibilità [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c0558-135">The following example uses the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view instead of the [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) compatibility view.</span></span>  
  
```  
CREATE PROCEDURE does_not_assume_caller_can_access_metadata  
WITH EXECUTE AS OWNER  
AS  
BEGIN  
SELECT name, id  
FROM sys.objects   
WHERE name = 'myTable'   
END;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c0558-136">Per passare temporaneamente al contesto di sicurezza del chiamante, è possibile utilizzare EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="c0558-136">You can use EXECUTE AS to temporarily switch to the security context of the caller.</span></span> <span data-ttu-id="c0558-137">Per altre informazioni, vedere [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0558-137">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span></span>  
  
## <a name="benefits-and-limits-of-metadata-visibility-configuration"></a><span data-ttu-id="c0558-138">Vantaggi e limiti della configurazione della visibilità dei metadati</span><span class="sxs-lookup"><span data-stu-id="c0558-138">Benefits and Limits of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="c0558-139">La configurazione della visibilità dei metadati svolge un ruolo importante per il piano di sicurezza globale.</span><span class="sxs-lookup"><span data-stu-id="c0558-139">Metadata visibility configuration can play an important role in your overall security plan.</span></span> <span data-ttu-id="c0558-140">In alcuni casi, tuttavia, un utente esperto potrebbe essere in grado di forzare la diffusione di alcuni metadati.</span><span class="sxs-lookup"><span data-stu-id="c0558-140">However, there are cases in which a skilled and determined user can force the disclosure of some metadata.</span></span> <span data-ttu-id="c0558-141">È pertanto consigliabile prevedere un ulteriore livello di protezione tramite l'implementazione di autorizzazioni per i metadati.</span><span class="sxs-lookup"><span data-stu-id="c0558-141">We recommend that you deploy metadata permissions as one of many defenses-in-depth.</span></span>  
  
 <span data-ttu-id="c0558-142">In teoria, è possibile forzare la creazione di metadati nei messaggi di errore modificando l'ordine di valutazione del predicato nelle query.</span><span class="sxs-lookup"><span data-stu-id="c0558-142">It is theoretically possible to force the emission of metadata in error messages by manipulating the order of predicate evaluation in queries.</span></span> <span data-ttu-id="c0558-143">La possibilità di *attacchi trial-and-error* di questo tipo non è specifica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="c0558-143">The possibility of such *trial-and-error attacks* is not specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c0558-144">ma è implicita nelle trasformazioni associative e commutative consentite nell'algebra relazionale.</span><span class="sxs-lookup"><span data-stu-id="c0558-144">It is implied by the associative and commutative transformations permitted in relational algebra.</span></span> <span data-ttu-id="c0558-145">È possibile ridurre questo rischio limitando le informazioni restituite nei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="c0558-145">You can mitigate this risk by limiting the information returned in error messages.</span></span> <span data-ttu-id="c0558-146">Per limitare ulteriormente la visibilità dei metadati in questo modo, è possibile avviare il server con il flag di traccia 3625,</span><span class="sxs-lookup"><span data-stu-id="c0558-146">To further restrict the visibility of metadata in this way, you can start the server with trace flag 3625.</span></span> <span data-ttu-id="c0558-147">che limita la quantità di informazioni visualizzate nei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="c0558-147">This trace flag limits the amount of information shown in error messages.</span></span> <span data-ttu-id="c0558-148">Questa soluzione contribuisce a limitare la diffusione forzata di informazioni,</span><span class="sxs-lookup"><span data-stu-id="c0558-148">In turn, this helps to prevent forced disclosures.</span></span> <span data-ttu-id="c0558-149">ma è controbilanciata dal fatto che i messaggi di errore saranno concisi e potrebbero essere difficili da utilizzare a scopi di debug.</span><span class="sxs-lookup"><span data-stu-id="c0558-149">The tradeoff is that error messages will be terse and might be difficult to use for debugging purposes.</span></span> <span data-ttu-id="c0558-150">Per altre informazioni, vedere [Opzioni di avvio del servizio del motore di database](../../database-engine/configure-windows/database-engine-service-startup-options.md) e [Flag di traccia &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0558-150">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) and [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
 <span data-ttu-id="c0558-151">I metadati seguenti non sono soggetti alla diffusione forzata:</span><span class="sxs-lookup"><span data-stu-id="c0558-151">The following metadata is not subject to forced disclosure:</span></span>  
  
-   <span data-ttu-id="c0558-152">Valore archiviato nella colonna **provider_string** di **sys.servers**.</span><span class="sxs-lookup"><span data-stu-id="c0558-152">The value stored in the **provider_string** column of **sys.servers**.</span></span> <span data-ttu-id="c0558-153">Un utente che non dispone dell'autorizzazione ALTER ANY LINKED SERVER sarà in grado di visualizzare unicamente un valore NULL in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="c0558-153">A user that does not have ALTER ANY LINKED SERVER permission will see a NULL value in this column.</span></span>  
  
-   <span data-ttu-id="c0558-154">La definizione dell'origine di un oggetto definito dall'utente, ad esempio una stored procedure o un trigger.</span><span class="sxs-lookup"><span data-stu-id="c0558-154">Source definition of a user-defined object such as a stored procedure or trigger.</span></span> <span data-ttu-id="c0558-155">Il codice sorgente è visibile solo se è vera una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0558-155">The source code is visible only when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="c0558-156">L'utente dispone dell'autorizzazione VIEW DEFINITION per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c0558-156">The user has VIEW DEFINITION permission on the object.</span></span>  
  
    -   <span data-ttu-id="c0558-157">All'utente non è stata negata l'autorizzazione VIEW DEFINITION per l'oggetto ed è stata concessa l'autorizzazione CONTROL, ALTER o TAKE OWNERSHIP per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c0558-157">The user has not been denied VIEW DEFINITION permission on the object and has CONTROL, ALTER, or TAKE OWNERSHIP permission on the object.</span></span> <span data-ttu-id="c0558-158">Per tutti gli altri utenti verranno visualizzati valori NULL.</span><span class="sxs-lookup"><span data-stu-id="c0558-158">All other users will see NULL.</span></span>  
  
-   <span data-ttu-id="c0558-159">Le colonne di definizione delle viste del catalogo seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0558-159">The definition columns found in the following catalog views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="c0558-160">**sys.all_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="c0558-160">**sys.all_sql_modules**</span></span>|<span data-ttu-id="c0558-161">**sys.sql_modules**</span><span class="sxs-lookup"><span data-stu-id="c0558-161">**sys.sql_modules**</span></span>|  
    |<span data-ttu-id="c0558-162">**sys.server_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="c0558-162">**sys.server_sql_modules**</span></span>|<span data-ttu-id="c0558-163">**sys.check_constraints**</span><span class="sxs-lookup"><span data-stu-id="c0558-163">**sys.check_constraints**</span></span>|  
    |<span data-ttu-id="c0558-164">**sys.default_constraints**</span><span class="sxs-lookup"><span data-stu-id="c0558-164">**sys.default_constraints**</span></span>|<span data-ttu-id="c0558-165">**sys.computed_columns**</span><span class="sxs-lookup"><span data-stu-id="c0558-165">**sys.computed_columns**</span></span>|  
    |<span data-ttu-id="c0558-166">**sys.numbered_procedures**</span><span class="sxs-lookup"><span data-stu-id="c0558-166">**sys.numbered_procedures**</span></span>||  
  
-   <span data-ttu-id="c0558-167">Colonna **ctext** nella vista di compatibilità **syscomments** .</span><span class="sxs-lookup"><span data-stu-id="c0558-167">The **ctext** column in the **syscomments** compatibility view.</span></span>  
  
-   <span data-ttu-id="c0558-168">Output della procedura **sp_helptext** .</span><span class="sxs-lookup"><span data-stu-id="c0558-168">The output of the **sp_helptext** procedure.</span></span>  
  
-   <span data-ttu-id="c0558-169">Le colonne seguenti nelle viste degli schemi delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="c0558-169">The following columns in the information schema views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="c0558-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span><span class="sxs-lookup"><span data-stu-id="c0558-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span></span>|<span data-ttu-id="c0558-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c0558-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="c0558-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c0558-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span></span>|<span data-ttu-id="c0558-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c0558-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="c0558-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c0558-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span></span>|<span data-ttu-id="c0558-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c0558-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span></span>|  
  
-   <span data-ttu-id="c0558-176">La funzione OBJECT_DEFINITION()</span><span class="sxs-lookup"><span data-stu-id="c0558-176">OBJECT_DEFINITION() function</span></span>  
  
-   <span data-ttu-id="c0558-177">Valore archiviato nella colonna password_hash di **sys.sql_logins**.</span><span class="sxs-lookup"><span data-stu-id="c0558-177">The value stored in the password_hash column of **sys.sql_logins**.</span></span>  <span data-ttu-id="c0558-178">Un utente che non dispone dell'autorizzazione CONTROL SERVER sarà in grado di visualizzare unicamente un valore NULL in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="c0558-178">A user that does not have CONTROL SERVER permission will see a NULL value in this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0558-179">Le definizioni SQL delle procedure e delle funzioni di sistema predefinite sono visibili a livello pubblico tramite la vista del catalogo **sys.system_sql_modules** , la stored procedure **sp_helptext** e la funzione OBJECT_DEFINITION().</span><span class="sxs-lookup"><span data-stu-id="c0558-179">The SQL definitions of built-in system procedures and functions are publicly visible through the **sys.system_sql_modules** catalog view, the **sp_helptext** stored procedure, and the OBJECT_DEFINITION() function.</span></span>  
  
## <a name="general-principles-of-metadata-visibility"></a><span data-ttu-id="c0558-180">Principi generali della visibilità dei metadati</span><span class="sxs-lookup"><span data-stu-id="c0558-180">General Principles of Metadata Visibility</span></span>  
 <span data-ttu-id="c0558-181">Di seguito sono illustrati alcuni principi generali da tenere in considerazione per la visibilità dei metadati:</span><span class="sxs-lookup"><span data-stu-id="c0558-181">The following are some general principles to consider regarding metadata visibility:</span></span>  
  
-   <span data-ttu-id="c0558-182">Autorizzazioni implicite dei ruoli predefiniti</span><span class="sxs-lookup"><span data-stu-id="c0558-182">Fixed roles implicit permissions</span></span>  
  
-   <span data-ttu-id="c0558-183">Ambito delle autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c0558-183">Scope of permissions</span></span>  
  
-   <span data-ttu-id="c0558-184">Precedenza di DENY</span><span class="sxs-lookup"><span data-stu-id="c0558-184">Precedence of DENY</span></span>  
  
-   <span data-ttu-id="c0558-185">Visibilità dei metadati dei sottocomponenti</span><span class="sxs-lookup"><span data-stu-id="c0558-185">Visibility of subcomponent metadata</span></span>  
  
### <a name="fixed-roles-and-implicit-permissions"></a><span data-ttu-id="c0558-186">Autorizzazioni implicite dei ruoli predefiniti</span><span class="sxs-lookup"><span data-stu-id="c0558-186">Fixed Roles and Implicit Permissions</span></span>  
 <span data-ttu-id="c0558-187">I metadati accessibili ai ruoli predefiniti variano in base alle autorizzazioni implicite corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c0558-187">Metadata that can be accessed by fixed roles depends upon their corresponding implicit permissions.</span></span>  
  
### <a name="scope-of-permissions"></a><span data-ttu-id="c0558-188">Ambito delle autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c0558-188">Scope of Permissions</span></span>  
 <span data-ttu-id="c0558-189">Le autorizzazioni valide in un ambito implicano la possibilità di visualizzare i metadati dell'ambito specifico e di tutti gli ambiti dipendenti.</span><span class="sxs-lookup"><span data-stu-id="c0558-189">Permissions at one scope imply the ability to see metadata at that scope and at all enclosed scopes.</span></span> <span data-ttu-id="c0558-190">Ad esempio, l'autorizzazione SELECT per uno schema implica che il beneficiario dispone dell'autorizzazione SELECT per tutte le entità a protezione diretta contenute nello schema specifico.</span><span class="sxs-lookup"><span data-stu-id="c0558-190">For example, SELECT permission on a schema implies that the grantee has SELECT permission on all securables that are contained by that schema.</span></span> <span data-ttu-id="c0558-191">Se si concede a un utente l'autorizzazione SELECT per uno schema, l'utente potrà pertanto visualizzare i metadati dello schema e tutte le tabelle, le viste, le funzioni, le procedure, le code nonché i sinonimi, i tipi e le raccolte XML Schema in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="c0558-191">The granting of SELECT permission on a schema therefore enables a user to see the metadata of the schema and also all tables, views, functions, procedures, queues, synonyms, types, and XML schema collections within it.</span></span> <span data-ttu-id="c0558-192">Per altre informazioni, vedere [Gerarchia delle autorizzazioni &#40;Motore di database&#41;](permissions-hierarchy-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c0558-192">For more information about scopes, see [Permissions Hierarchy &#40;Database Engine&#41;](permissions-hierarchy-database-engine.md).</span></span>  
  
### <a name="precedence-of-deny"></a><span data-ttu-id="c0558-193">Precedenza di DENY</span><span class="sxs-lookup"><span data-stu-id="c0558-193">Precedence of DENY</span></span>  
 <span data-ttu-id="c0558-194">DENY ha in genere la precedenza sulle altre autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c0558-194">DENY typically takes precedence over other permissions.</span></span> <span data-ttu-id="c0558-195">Ad esempio, se a un utente del database viene concessa l'autorizzazione EXECUTE per uno schema, ma gli viene negata l'autorizzazione EXECUTE per una stored procedure dello schema specifico, l'utente non potrà visualizzare i metadati relativi alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c0558-195">For example, if a database user is granted EXECUTE permission on a schema but has been denied EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="c0558-196">Inoltre, se a un utente viene negata l'autorizzazione EXECUTE per uno schema ma viene concessa l'autorizzazione EXECUTE per una stored procedure dello schema specifico, l'utente non potrà visualizzare i metadati relativi alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c0558-196">Additionally, if a user is denied EXECUTE permission on a schema but has been granted EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="c0558-197">Infine, se a un utente viene concessa e negata l'autorizzazione EXECUTE per una stored procedure, cosa che può accadere nel caso di appartenenza a diversi ruoli, DENY ha la precedenza e l'utente non potrà visualizzare i metadati della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c0558-197">For another example, if a user has been granted and denied EXECUTE permission on a stored procedure, which is possible through your various role memberships, DENY takes precedence and the user cannot view the metadata of the stored procedure.</span></span>  
  
### <a name="visibility-of-subcomponent-metadata"></a><span data-ttu-id="c0558-198">Visibilità dei metadati dei sottocomponenti</span><span class="sxs-lookup"><span data-stu-id="c0558-198">Visibility of Subcomponent Metadata</span></span>  
 <span data-ttu-id="c0558-199">La visibilità dei sottocomponenti, quali gli indici, i vincoli CHECK e i trigger, è determinata dalle autorizzazioni per il componente padre.</span><span class="sxs-lookup"><span data-stu-id="c0558-199">The visibility of subcomponents, such as indexes, check constraints, and triggers is determined by permissions on the parent.</span></span> <span data-ttu-id="c0558-200">A questi sottocomponenti non è possibile concedere autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c0558-200">These subcomponents do not have grantable permissions.</span></span> <span data-ttu-id="c0558-201">Ad esempio, se a un utente sono state concesse autorizzazioni per una tabella, l'utente potrà visualizzare i metadati relativi a tabelle, colonne, indici, vincoli CHECK, trigger e altri sottocomponenti.</span><span class="sxs-lookup"><span data-stu-id="c0558-201">For example, if a user has been granted some permission on a table, the user can view the metadata for the tables, columns, indexes, check constraints, triggers, and other such subcomponents.</span></span>  
  
#### <a name="metadata-that-is-accessible-to-all-database-users"></a><span data-ttu-id="c0558-202">Metadati accessibili a tutti gli utenti del database</span><span class="sxs-lookup"><span data-stu-id="c0558-202">Metadata That Is Accessible to All Database Users</span></span>  
 <span data-ttu-id="c0558-203">Alcuni metadati devono essere accessibili a tutti gli utenti di un database specifico.</span><span class="sxs-lookup"><span data-stu-id="c0558-203">Some metadata must be accessible to all users in a specific database.</span></span> <span data-ttu-id="c0558-204">Ad esempio, non è possibile concedere autorizzazioni per i filegroup e pertanto non è possibile concedere a un utente l'autorizzazione per la visualizzazione dei metadati di un filegroup.</span><span class="sxs-lookup"><span data-stu-id="c0558-204">For example, filegroups do not have conferrable permissions; therefore, a user cannot be granted permission to view the metadata of a filegroup.</span></span> <span data-ttu-id="c0558-205">Tutti gli utenti che possono creare una tabella devono tuttavia essere in grado di accedere ai metadati dei filegroup per poter usare le clausole *filegroup* ON o *filegroup* TEXTIMAGE_ON dell'istruzione CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="c0558-205">However, any user that can create a table must be able to access filegroup metadata to use the ON *filegroup* or TEXTIMAGE_ON *filegroup* clauses of the CREATE TABLE statement.</span></span>  
  
 <span data-ttu-id="c0558-206">I metadati restituiti dalle funzioni DB_ID() e DB_NAME() sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c0558-206">The metadata that is returned by the DB_ID() and DB_NAME() functions is visible to all users.</span></span>  
  
 <span data-ttu-id="c0558-207">Nella tabella seguente sono elencate le viste del catalogo visibili al ruolo **pubblico** .</span><span class="sxs-lookup"><span data-stu-id="c0558-207">The following table lists the catalog views that are visible to the **public** role.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0558-208">**sys.partition_functions**</span><span class="sxs-lookup"><span data-stu-id="c0558-208">**sys.partition_functions**</span></span>|<span data-ttu-id="c0558-209">**sys.partition_range_values**</span><span class="sxs-lookup"><span data-stu-id="c0558-209">**sys.partition_range_values**</span></span>|  
|<span data-ttu-id="c0558-210">**sys.partition_schemes**</span><span class="sxs-lookup"><span data-stu-id="c0558-210">**sys.partition_schemes**</span></span>|<span data-ttu-id="c0558-211">**sys.data_spaces**</span><span class="sxs-lookup"><span data-stu-id="c0558-211">**sys.data_spaces**</span></span>|  
|<span data-ttu-id="c0558-212">**sys.filegroups**</span><span class="sxs-lookup"><span data-stu-id="c0558-212">**sys.filegroups**</span></span>|<span data-ttu-id="c0558-213">**sys.destination_data_spaces**</span><span class="sxs-lookup"><span data-stu-id="c0558-213">**sys.destination_data_spaces**</span></span>|  
|<span data-ttu-id="c0558-214">**sys.database_files**</span><span class="sxs-lookup"><span data-stu-id="c0558-214">**sys.database_files**</span></span>|<span data-ttu-id="c0558-215">**sys.allocation_units**</span><span class="sxs-lookup"><span data-stu-id="c0558-215">**sys.allocation_units**</span></span>|  
|<span data-ttu-id="c0558-216">**sys.partitions**</span><span class="sxs-lookup"><span data-stu-id="c0558-216">**sys.partitions**</span></span>|<span data-ttu-id="c0558-217">**sys.messages**</span><span class="sxs-lookup"><span data-stu-id="c0558-217">**sys.messages**</span></span>|  
|<span data-ttu-id="c0558-218">**sys.schemas**</span><span class="sxs-lookup"><span data-stu-id="c0558-218">**sys.schemas**</span></span>|<span data-ttu-id="c0558-219">**sys.configurations**</span><span class="sxs-lookup"><span data-stu-id="c0558-219">**sys.configurations**</span></span>|  
|<span data-ttu-id="c0558-220">**sys.sql_dependencies**</span><span class="sxs-lookup"><span data-stu-id="c0558-220">**sys.sql_dependencies**</span></span>|<span data-ttu-id="c0558-221">**sys.type_assembly_usages**</span><span class="sxs-lookup"><span data-stu-id="c0558-221">**sys.type_assembly_usages**</span></span>|  
|<span data-ttu-id="c0558-222">**sys.parameter_type_usages**</span><span class="sxs-lookup"><span data-stu-id="c0558-222">**sys.parameter_type_usages**</span></span>|<span data-ttu-id="c0558-223">**sys.column_type_usages**</span><span class="sxs-lookup"><span data-stu-id="c0558-223">**sys.column_type_usages**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0558-224">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0558-224">See Also</span></span>  
 <span data-ttu-id="c0558-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0558-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 <span data-ttu-id="c0558-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0558-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span></span>  
 <span data-ttu-id="c0558-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0558-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="c0558-228">[Clausola EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0558-228">[EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span></span>  
 <span data-ttu-id="c0558-229">[Viste del catalogo &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0558-229">[Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="c0558-230">Viste della compatibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c0558-230">Compatibility Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql)  
  
  
