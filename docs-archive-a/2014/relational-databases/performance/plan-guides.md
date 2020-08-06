---
title: Guide di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- SQL plan guides
- OPTIMIZE FOR query hint
- RECOMPILE query hint
- OBJECT plan guide
- plan guides [SQL Server], about plan guides
- OPTION clause
- plan guides [SQL Server]
- USE PLAN query hint
ms.assetid: bfc97632-c14c-4768-9dc5-a9c512f6b2bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c97682163313a56acb8521174fa8d4012a69b529
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634997"
---
# <a name="plan-guides"></a><span data-ttu-id="bc686-102">Guide di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-102">Plan Guides</span></span>
  <span data-ttu-id="bc686-103">Le guide di piano consentono di ottimizzare le prestazioni delle query quando non è possibile o non si desidera modificare direttamente il testo della query corrente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc686-103">Plan guides let you optimize the performance of queries when you cannot or do not want to directly change the text of the actual query in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="bc686-104">Le guide di piano influiscono sull'ottimizzazione delle query mediante l'aggiunta di hint per la query o di un piano di query fisso.</span><span class="sxs-lookup"><span data-stu-id="bc686-104">Plan guides influence the optimization of queries by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="bc686-105">Le guide di piano risultano utili quando le prestazioni di un piccolo subset di query eseguite su un database di terze parti sono inferiori a quelle previste.</span><span class="sxs-lookup"><span data-stu-id="bc686-105">Plan guides can be useful when a small subset of queries in a database application provided by a third-party vendor are not performing as expected.</span></span> <span data-ttu-id="bc686-106">In una guida di piano, viene specificata l'istruzione Transact-SQL da ottimizzare e la clausola OPTION che contiene gli hint per la query da utilizzare o un piano di query specifico da utilizzare per ottimizzare la query.</span><span class="sxs-lookup"><span data-stu-id="bc686-106">In the plan guide, you specify the Transact-SQL statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="bc686-107">Quando viene eseguita la query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associa l'istruzione Transact-SQL alla guida di piano e, in fase di esecuzione, associa la clausola OPTION alla query oppure utilizza il piano di query specificato.</span><span class="sxs-lookup"><span data-stu-id="bc686-107">When the query executes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] matches the Transact-SQL statement to the plan guide and attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="bc686-108">Il numero totale di guide di piano che è possibile creare è limitato solo dalle risorse di sistema disponibili.</span><span class="sxs-lookup"><span data-stu-id="bc686-108">The total number of plan guides you can create is limited only by available system resources.</span></span> <span data-ttu-id="bc686-109">È comunque consigliabile utilizzare le guide di piano per le sole query critiche di cui si desidera migliorare o stabilizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="bc686-109">Nevertheless, plan guides should be limited to mission-critical queries that are targeted for improved or stabilized performance.</span></span> <span data-ttu-id="bc686-110">Le guide di piano non vanno utilizzate per modificare la maggior parte del carico di query di un'applicazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="bc686-110">Plan guides should not be used to influence most of the query load of a deployed application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc686-111">Le guide di piano sono supportate solo in alcune edizioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc686-111">Plan guides cannot be used in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bc686-112">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="bc686-112">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="bc686-113">Le guide di piano sono visibili in qualsiasi edizione.</span><span class="sxs-lookup"><span data-stu-id="bc686-113">Plan guides are visible in any edition.</span></span> <span data-ttu-id="bc686-114">È inoltre possibile collegare un database che contiene guide di piano a qualsiasi edizione.</span><span class="sxs-lookup"><span data-stu-id="bc686-114">You can also attach a database that contains plan guides to any edition.</span></span> <span data-ttu-id="bc686-115">Quando si ripristina o si collega un database a una versione aggiornata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le guide di piano non vengono modificate.</span><span class="sxs-lookup"><span data-stu-id="bc686-115">Plan guides remain intact when you restore or attach a database to an upgraded version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="types-of-plan-guides"></a><span data-ttu-id="bc686-116">Tipi di guide di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-116">Types of Plan Guides</span></span>  
 <span data-ttu-id="bc686-117">È possibile creare i seguenti tipi di guide di piano:</span><span class="sxs-lookup"><span data-stu-id="bc686-117">The following types of plan guides can be created.</span></span>  
  
 <span data-ttu-id="bc686-118">guida di piano di tipo OBJECT</span><span class="sxs-lookup"><span data-stu-id="bc686-118">OBJECT plan guide</span></span>  
 <span data-ttu-id="bc686-119">Una guida di piano di tipo OBJECT corrisponde alle query eseguite nel contesto di stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] , funzioni scalari definite dall'utente, funzioni con valori di tabella definite dall'utente con istruzioni multiple e trigger DML.</span><span class="sxs-lookup"><span data-stu-id="bc686-119">An OBJECT plan guide matches queries that execute in the context of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, scalar user-defined functions, multi-statement table-valued user-defined functions, and DML triggers.</span></span>  
  
 <span data-ttu-id="bc686-120">Si supponga che la seguente stored procedure, che accetta il parametro `@Country`_`region` , si trovi in un'applicazione di database distribuita sul database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bc686-120">Suppose the following stored procedure, which takes the `@Country`_`region` parameter, is in a database application that is deployed against the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
CREATE PROCEDURE Sales.GetSalesOrderByCountry (@Country_region nvarchar(60))  
AS  
BEGIN  
    SELECT *  
    FROM Sales.SalesOrderHeader AS h, Sales.Customer AS c,   
        Sales.SalesTerritory AS t  
    WHERE h.CustomerID = c.CustomerID  
        AND c.TerritoryID = t.TerritoryID  
        AND CountryRegionCode = @Country_region  
END;  
```  
  
 <span data-ttu-id="bc686-121">Questa stored procedure è stata compilata e ottimizzata per `@Country`_`region = N'AU'` (Australia).</span><span class="sxs-lookup"><span data-stu-id="bc686-121">Assume that this stored procedure has been compiled and optimized for `@Country`_`region = N'AU'` (Australia).</span></span> <span data-ttu-id="bc686-122">Tuttavia, poiché sono presenti relativamente pochi ordini di vendita con origine in Australia, le prestazioni diminuiscono quando viene eseguita la query utilizzando i valori del parametro dei paesi con più ordini di vendita.</span><span class="sxs-lookup"><span data-stu-id="bc686-122">However, because there are relatively few sales orders that originate from Australia, performance decreases when the query executes using parameter values of countries with more sales orders.</span></span> <span data-ttu-id="bc686-123">Poiché il paese da cui proviene la maggior parte degli ordini di vendita sono gli Stati Uniti, un piano di query generato per `@Country`\_`region = N'US'` offrirebbe probabilmente prestazioni migliori per tutti i possibili valori del parametro `@Country`\_`region` .</span><span class="sxs-lookup"><span data-stu-id="bc686-123">Because the most sales orders originate in the United States, a query plan that is generated for `@Country`\_`region = N'US'` would likely perform better for all possible values of the `@Country`\_`region` parameter.</span></span>  
  
 <span data-ttu-id="bc686-124">Per risolvere il problema è possibile modificare la stored procedure aggiungendo alla query l'hint `OPTIMIZE FOR` .</span><span class="sxs-lookup"><span data-stu-id="bc686-124">You could address this problem by modifying the stored procedure to add the `OPTIMIZE FOR` query hint to the query.</span></span> <span data-ttu-id="bc686-125">Poiché la stored procedure si trova in un'applicazione distribuita, non è possibile modificare direttamente il codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc686-125">However, because the stored procedure is in a deployed application, you cannot directly modify the application code.</span></span> <span data-ttu-id="bc686-126">È invece possibile creare la guida di piano seguente nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc686-126">Instead, you can create the following plan guide in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT *FROM Sales.SalesOrderHeader AS h,  
        Sales.Customer AS c,  
        Sales.SalesTerritory AS t  
        WHERE h.CustomerID = c.CustomerID   
            AND c.TerritoryID = t.TerritoryID  
            AND CountryRegionCode = @Country_region',  
@type = N'OBJECT',  
@module_or_batch = N'Sales.GetSalesOrderByCountry',  
@params = NULL,  
@hints = N'OPTION (OPTIMIZE FOR (@Country_region = N''US''))';  
```  
  
 <span data-ttu-id="bc686-127">Al momento dell'esecuzione della query specificata nell'istruzione `sp_create_plan_guide` , la query viene modificata prima dell'ottimizzazione per includere la clausola `OPTIMIZE FOR (@Country = N''US'')` .</span><span class="sxs-lookup"><span data-stu-id="bc686-127">When the query specified in the `sp_create_plan_guide` statement executes, the query is modified before optimization to include the `OPTIMIZE FOR (@Country = N''US'')` clause.</span></span>  
  
 <span data-ttu-id="bc686-128">Guida di piano di tipo SQL</span><span class="sxs-lookup"><span data-stu-id="bc686-128">SQL plan guide</span></span>  
 <span data-ttu-id="bc686-129">Una guida di piano di tipo SQL corrisponde alle query eseguite nel contesto di batch e istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] autonome che non fanno parte di un oggetto di database.</span><span class="sxs-lookup"><span data-stu-id="bc686-129">An SQL plan guide matches queries that execute in the context of stand-alone [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and batches that are not part of a database object.</span></span> <span data-ttu-id="bc686-130">Le guide di piano basate su SQL possono inoltre essere utilizzate per query con parametrizzazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="bc686-130">SQL-based plan guides can also be used to match queries that parameterize to a specified form.</span></span> <span data-ttu-id="bc686-131">Le guide di piano di tipo SQL vengono applicate a istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] autonome e batch.</span><span class="sxs-lookup"><span data-stu-id="bc686-131">SQL plan guides apply to stand-alone [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and batches.</span></span> <span data-ttu-id="bc686-132">Spesso tali istruzioni vengono inoltrate da un'applicazione mediante la stored procedure di sistema [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="bc686-132">Frequently, these statements are submitted by an application by using the [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) system stored procedure.</span></span> <span data-ttu-id="bc686-133">Ad esempio, si consideri il batch autonomo seguente:</span><span class="sxs-lookup"><span data-stu-id="bc686-133">For example, consider the following stand-alone batch:</span></span>  
  
```  
SELECT TOP 1 * FROM Sales.SalesOrderHeader ORDER BY OrderDate DESC;  
```  
  
 <span data-ttu-id="bc686-134">Per impedire la generazione di un piano di esecuzione parallelo su questa query, creare la seguente guida di piano e impostare l'hint per la query `MAXDOP` su `1` nel parametro `@hints` .</span><span class="sxs-lookup"><span data-stu-id="bc686-134">To prevent a parallel execution plan from being generated on this query, create the following plan guide and set the `MAXDOP` query hint to `1` in the `@hints` parameter.</span></span>  
  
```  
sp_create_plan_guide   
@name = N'Guide2',   
@stmt = N'SELECT TOP 1 * FROM Sales.SalesOrderHeader ORDER BY OrderDate DESC',  
@type = N'SQL',  
@module_or_batch = NULL,   
@params = NULL,   
@hints = N'OPTION (MAXDOP 1)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bc686-135">I valori specificati per gli argomenti `@module_or_batch` e `@params` dell'istruzione `sp_create_plan guide` devono corrispondere al testo specificato nella query effettiva.</span><span class="sxs-lookup"><span data-stu-id="bc686-135">The values that are supplied for the `@module_or_batch` and `@params` arguments of the `sp_create_plan guide` statement must match the corresponding text submitted in the actual query.</span></span> <span data-ttu-id="bc686-136">Per altre informazioni, vedere [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) e [Usare SQL Server Profiler per creare e testare guide di piano](plan-guides.md).</span><span class="sxs-lookup"><span data-stu-id="bc686-136">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) and [Use SQL Server Profiler to Create and Test Plan Guides](plan-guides.md).</span></span>  
  
 <span data-ttu-id="bc686-137">È possibile creare guide di piano SQL anche per le query con parametrizzazione forzata quando l'opzione di database PARAMETERIZATION è impostata su FORCED, oppure quando si crea una guida di piano di tipo TEMPLATE per specificare la parametrizzazione di una classe di query.</span><span class="sxs-lookup"><span data-stu-id="bc686-137">SQL plan guides can also be created on queries that parameterize to the same form when the PARAMETERIZATION database option is SET to FORCED, or when a TEMPLATE plan guide is created specifying that a parameterized class of queries.</span></span>  
  
 <span data-ttu-id="bc686-138">TEMPLATE - guida di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-138">TEMPLATE plan guide</span></span>  
 <span data-ttu-id="bc686-139">Una guida di piano di tipo TEMPLATE corrisponde alle query autonome con parametrizzazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="bc686-139">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span> <span data-ttu-id="bc686-140">Tali guide di piano vengono utilizzate per sostituire l'opzione SET di database PARAMETERIZATION di un database per una classe di query.</span><span class="sxs-lookup"><span data-stu-id="bc686-140">These plan guides are used to override the current PARAMETERIZATION database SET option of a database for a class of queries.</span></span>  
  
 <span data-ttu-id="bc686-141">È possibile creare una guida di piano di tipo TEMPLATE nelle seguenti situazioni:</span><span class="sxs-lookup"><span data-stu-id="bc686-141">You can create a TEMPLATE plan guide in either of the following situations:</span></span>  
  
-   <span data-ttu-id="bc686-142">L'opzione di database PARAMETERIZATION è impostata su FORCED, ma si desidera compilare alcune query in base alle regole della parametrizzazione semplice.</span><span class="sxs-lookup"><span data-stu-id="bc686-142">The PARAMETERIZATION database option is SET to FORCED, but there are queries you want compiled according to the rules of simple parameterization.</span></span>  
  
-   <span data-ttu-id="bc686-143">L'opzione di database PARAMETERIZATION è impostata su SIMPLE (impostazione predefinita), ma si desidera che una classe di query venga sottoposta a parametrizzazione forzata.</span><span class="sxs-lookup"><span data-stu-id="bc686-143">The PARAMETERIZATION database option is SET to SIMPLE (the default setting), but you want forced parameterization to be tried on a class of queries.</span></span>  
  
## <a name="plan-guide-matching-requirements"></a><span data-ttu-id="bc686-144">Requisiti di corrispondenza per la guida di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-144">Plan Guide Matching Requirements</span></span>  
 <span data-ttu-id="bc686-145">Le guide di piano sono definite a livello di ambito del database in cui vengono create.</span><span class="sxs-lookup"><span data-stu-id="bc686-145">Plan guides are scoped to the database in which they are created.</span></span> <span data-ttu-id="bc686-146">Pertanto, è possibile far corrispondere alla query solo le guide di piano presenti nel database corrente al momento dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="bc686-146">Therefore, only plan guides that are in the database that is current when a query executes can be matched to the query.</span></span> <span data-ttu-id="bc686-147">Ad esempio, se [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] è il database corrente e viene eseguita la query seguente:</span><span class="sxs-lookup"><span data-stu-id="bc686-147">For example, if [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] is the current database and the following query executes:</span></span>  
  
 `SELECT FirstName, LastName FROM Person.Person;`  
  
 <span data-ttu-id="bc686-148">È possibile far corrispondere alla query solo le guide di piano nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc686-148">Only plan guides in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database are eligible to be matched to this query.</span></span> <span data-ttu-id="bc686-149">Se tuttavia il database corrente è [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e vengono eseguite le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc686-149">However, if [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] is the current database and the following statements are run:</span></span>  
  
 `USE DB1;`  
  
 `SELECT FirstName, LastName FROM Person.Person;`  
  
 <span data-ttu-id="bc686-150">È possibile far corrispondere alla query solo le guide di piano in `DB1` , poiché la query è in esecuzione nel contesto di `DB1`.</span><span class="sxs-lookup"><span data-stu-id="bc686-150">Only plan guides in `DB1` are eligible to be matched to the query because the query is executing in the context of `DB1`.</span></span>  
  
 <span data-ttu-id="bc686-151">Per guide di piano basate su SQL o TEMPLATE, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue la corrispondenza tra i valori per gli argomenti @module_or_batch e @params e una query, confrontando i due valori carattere per carattere.</span><span class="sxs-lookup"><span data-stu-id="bc686-151">For SQL- or TEMPLATE-based plan guides, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] matches the values for the @module_or_batch and @params arguments to a query by comparing the two values character by character.</span></span> <span data-ttu-id="bc686-152">Per questo motivo è necessario immettere il testo esattamente come [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lo riceve nel batch.</span><span class="sxs-lookup"><span data-stu-id="bc686-152">This means you must provide the text exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it in the actual batch.</span></span>  
  
 <span data-ttu-id="bc686-153">Se @type = 'SQL' e @module_or_batch vengono impostate su NULL, il valore di @module_or_batch viene impostato sul valore di @stmt. Di conseguenza, il valore per *statement_text* deve essere specificato nello stesso formato, carattere per carattere, così come viene inviato a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc686-153">When @type = 'SQL' and @module_or_batch is set to NULL, the value of @module_or_batch is set to the value of @stmt. This means that the value for *statement_text* must be provided in the identical format, character-for-character, as it is submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bc686-154">Per semplificare questa corrispondenza, non viene eseguita alcuna conversione interna.</span><span class="sxs-lookup"><span data-stu-id="bc686-154">No internal conversion is performed to facilitate this match.</span></span>  
  
 <span data-ttu-id="bc686-155">Quando è possibile applicare sia una guida di piano normale (SQL o OBJECT) sia una guida di piano TEMPLATE a un'istruzione, verrà utilizzata solo la guida di piano normale.</span><span class="sxs-lookup"><span data-stu-id="bc686-155">When both a regular (SQL or OBJECT) plan guide and a TEMPLATE plan guide can apply to a statement, only the regular plan guide will be used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc686-156">Il batch contenente l'istruzione sulla quale si desidera creare una guida di piano non può contenere un'istruzione USE *database* .</span><span class="sxs-lookup"><span data-stu-id="bc686-156">The batch that contains the statement on which you want to create a plan guide cannot contain a USE *database* statement.</span></span>  
  
## <a name="plan-guide-effect-on-the-plan-cache"></a><span data-ttu-id="bc686-157">Effetto delle guide di piano sulla cache dei piani</span><span class="sxs-lookup"><span data-stu-id="bc686-157">Plan Guide Effect on the Plan Cache</span></span>  
 <span data-ttu-id="bc686-158">La creazione di una guida di piano su un modulo rimuove il piano di query per il dato modulo dalla cache dei piani.</span><span class="sxs-lookup"><span data-stu-id="bc686-158">Creating a plan guide on a module removes the query plan for that module from the plan cache.</span></span> <span data-ttu-id="bc686-159">La creazione di una guida di piano di tipo OBJECT o SQL su un batch rimuove il piano di query per un batch con lo stesso valore hash.</span><span class="sxs-lookup"><span data-stu-id="bc686-159">Creating a plan guide of type OBJECT or SQL on a batch removes the query plan for a batch that has the same hash value.</span></span> <span data-ttu-id="bc686-160">La creazione di una guida di piano di tipo TEMPLATE rimuove tutti i batch a istruzione singola dalla cache dei piani all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="bc686-160">Creating a plan guide of type TEMPLATE removes all single-statement batches from the plan cache within that database.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="bc686-161">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="bc686-161">Related Tasks</span></span>  
  
|<span data-ttu-id="bc686-162">Attività</span><span class="sxs-lookup"><span data-stu-id="bc686-162">Task</span></span>|<span data-ttu-id="bc686-163">Argomento</span><span class="sxs-lookup"><span data-stu-id="bc686-163">Topic</span></span>|  
|----------|-----------|  
|<span data-ttu-id="bc686-164">Viene descritto come creare una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="bc686-164">Describes how to create a plan guide.</span></span>|[<span data-ttu-id="bc686-165">Creare una nuova guida di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-165">Create a New Plan Guide</span></span>](create-a-new-plan-guide.md)|  
|<span data-ttu-id="bc686-166">Viene descritto come creare una guida di piano per le query con parametri.</span><span class="sxs-lookup"><span data-stu-id="bc686-166">Describes how to create a plan guide for parameterized queries.</span></span>|[<span data-ttu-id="bc686-167">Creare una guida di piano per le query con parametri</span><span class="sxs-lookup"><span data-stu-id="bc686-167">Create a Plan Guide for Parameterized Queries</span></span>](create-a-plan-guide-for-parameterized-queries.md)|  
|<span data-ttu-id="bc686-168">Viene descritto come controllare il comportamento di parametrizzazione delle query utilizzando guide di piano.</span><span class="sxs-lookup"><span data-stu-id="bc686-168">Describes how to control query parameterization behavior by using plan guides.</span></span>|[<span data-ttu-id="bc686-169">Specificare il comportamento di parametrizzazione delle query tramite guide di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-169">Specify Query Parameterization Behavior by Using Plan Guides</span></span>](specify-query-parameterization-behavior-by-using-plan-guides.md)|  
|<span data-ttu-id="bc686-170">Viene descritto come includere un piano di query fisso in una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="bc686-170">Describes how to include a fixed query plan in a plan guide.</span></span>|[<span data-ttu-id="bc686-171">Applicare un piano di query fisso a una guida di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-171">Apply a Fixed Query Plan to a Plan Guide</span></span>](apply-a-fixed-query-plan-to-a-plan-guide.md)|  
|<span data-ttu-id="bc686-172">Viene descritto come specificare hint per la query in una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="bc686-172">Describes how to specify query hints in a plan guide.</span></span>|[<span data-ttu-id="bc686-173">Associare gli hint per le query a una guida di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-173">Attach Query Hints to a Plan Guide</span></span>](attach-query-hints-to-a-plan-guide.md)|  
|<span data-ttu-id="bc686-174">Viene descritto come visualizzare le proprietà di una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="bc686-174">Describes how to view plan guide properties.</span></span>|[<span data-ttu-id="bc686-175">Visualizzare le proprietà delle guide di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-175">View Plan Guide Properties</span></span>](view-plan-guide-properties.md)|  
|<span data-ttu-id="bc686-176">Viene descritto come utilizzare SQL Server Profiler per creare e testare guide di piano.</span><span class="sxs-lookup"><span data-stu-id="bc686-176">Describes how to use SQL Server Profiler to create and test plan guides.</span></span>|[<span data-ttu-id="bc686-177">Usare SQL Server Profiler per creare e testare guide di piano</span><span class="sxs-lookup"><span data-stu-id="bc686-177">Use SQL Server Profiler to Create and Test Plan Guides</span></span>](plan-guides.md)|  
|<span data-ttu-id="bc686-178">Viene descritto come convalidare una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="bc686-178">Describes how to validate plan guides.</span></span>|[<span data-ttu-id="bc686-179">Convalidare le guide di piano dopo l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="bc686-179">Validate Plan Guides After Upgrade</span></span>](validate-plan-guides-after-upgrade.md)|  
  
## <a name="see-also"></a><span data-ttu-id="bc686-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc686-180">See Also</span></span>  
 <span data-ttu-id="bc686-181">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bc686-181">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="bc686-182">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bc686-182">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 <span data-ttu-id="bc686-183">[sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bc686-183">[sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="bc686-184">[sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bc686-184">[sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql) </span></span>  
 [<span data-ttu-id="bc686-185">sys.fn_validate_plan_guide &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bc686-185">sys.fn_validate_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql)  
  
  
