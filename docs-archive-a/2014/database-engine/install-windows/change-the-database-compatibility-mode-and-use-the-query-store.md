---
title: Migrare piani di query | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- query plans [SQL Server], migrating
- upgrading SQL Server, migrating query plans
- plan guides [SQL Server], migrating query plans
ms.assetid: 7e02a137-6867-4f6a-a45a-2b02674f7e65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dafd3a5f8a460bb08e63919c2cb853ad74dc2f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718684"
---
# <a name="migrate-query-plans"></a><span data-ttu-id="a6cb2-102">Migrare piani di query</span><span class="sxs-lookup"><span data-stu-id="a6cb2-102">Migrate Query Plans</span></span>
  <span data-ttu-id="a6cb2-103">Nella maggior parte dei casi, l'aggiornamento di un database alla versione più recente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comporta un miglioramento delle prestazioni di esecuzione delle query.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-103">In most cases, upgrading a database to the most recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will result in improved query performance.</span></span> <span data-ttu-id="a6cb2-104">Tuttavia, se sono presenti query critiche attentamente ottimizzate per le prestazioni, potrebbe essere necessario mantenere i piani per tali query prima di eseguire l'aggiornamento creando una guida di piano per ciascuna query.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-104">However, if you have mission-critical queries that have been carefully tuned for performance, you may want to preserve the query plans for these queries before upgrading by creating a plan guide for each query.</span></span> <span data-ttu-id="a6cb2-105">Se, dopo aver eseguito l'aggiornamento, Query Optimizer sceglie un piano meno efficiente per una o più query, è possibile abilitare le guide di piano e forzare il Query Optimizer a utilizzare i piani precedenti all'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-105">If, after upgrading, the query optimizer chooses a less efficient plan for one or more of the queries, you can enable the plan guides and force the query optimizer to use the pre-upgrade plans.</span></span>  
  
 <span data-ttu-id="a6cb2-106">Per creare guide di piano prima di eseguire l'aggiornamento, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a6cb2-106">To create plan guides before upgrading follow these steps:</span></span>  
  
1.  <span data-ttu-id="a6cb2-107">Registrare il piano corrente per ogni query mission-critical usando il [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure e specificando il piano di query nell'hint per la query USE PLAN.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-107">Record the current plan for each mission critical query by using the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure and specifying the query plan in the USE PLAN query hint.</span></span>  
  
2.  <span data-ttu-id="a6cb2-108">Verificare che la guida di piano sia applicata alla query.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-108">Verify that the plan guide is applied to the query.</span></span>  
  
3.  <span data-ttu-id="a6cb2-109">Aggiornare il database alla versione più recente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6cb2-109">Upgrade the database to the newer version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="a6cb2-110">I piani sono persistenti nel database aggiornato nelle guide di piano e vengono utilizzati come fallback in caso di regressioni del piano dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-110">The plans are persisted in the upgraded database in the plan guides and serve as a fallback in case of plan regressions after the upgrade.</span></span>  
  
     <span data-ttu-id="a6cb2-111">Si consiglia di non abilitare le guide di piano dopo l'aggiornamento, in quanto si potrebbero perdere opportunità per migliori piani nella nuova versione o ricompilazioni vantaggiose grazie a statistiche aggiornate.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-111">We recommend that you not enable the plan guides after the upgrade because you might miss opportunities for better plans in the new release or beneficial recompiles due to updated statistics.</span></span>  
  
4.  <span data-ttu-id="a6cb2-112">Se vengono scelti piani meno efficienti dopo l'aggiornamento, attivare tutte o un subset delle guide di piano per sostituire i nuovi piani.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-112">If less efficient plans are chosen after the upgrade, activate all or a subset of the plan guides to override the new plans.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6cb2-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6cb2-113">Example</span></span>  
 <span data-ttu-id="a6cb2-114">Nel seguente esempio viene illustrato come registrare un piano prima dell'aggiornamento per una query creando una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-114">The following example shows how to record a pre-upgrade plan for a query by creating a plan guide.</span></span>  
  
### <a name="step-1-collect-the-plan"></a><span data-ttu-id="a6cb2-115">Passaggio 1: Raccolta del piano</span><span class="sxs-lookup"><span data-stu-id="a6cb2-115">Step 1: Collect the Plan</span></span>  
 <span data-ttu-id="a6cb2-116">Il piano di query registrato nella guida di piano deve essere in formato XML.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-116">The query plan recorded in the plan guide must be in XML format.</span></span> <span data-ttu-id="a6cb2-117">È possibile creare piani di query in formato XML nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="a6cb2-117">XML-formatted query plans can be produced through the following ways:</span></span>  
  
-   [<span data-ttu-id="a6cb2-118">SET SHOWPLAN_XML</span><span class="sxs-lookup"><span data-stu-id="a6cb2-118">SET SHOWPLAN_XML</span></span>](/sql/t-sql/statements/set-showplan-xml-transact-sql)  
  
-   [<span data-ttu-id="a6cb2-119">SET STATISTICS XML</span><span class="sxs-lookup"><span data-stu-id="a6cb2-119">SET STATISTICS XML</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
-   <span data-ttu-id="a6cb2-120">Esecuzione di query sulla colonna query_plan della funzione a gestione dinamica [sys. dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a6cb2-120">Querying the query_plan column of the [sys.dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) dynamic management function.</span></span>  
  
-   <span data-ttu-id="a6cb2-121">[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Classi di evento [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md)e [Showplan XML for Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="a6cb2-121">The [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md), and [Showplan XML For Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) event classes.</span></span>  
  
 <span data-ttu-id="a6cb2-122">Nell'esempio seguente viene raccolto il piano di query per l'istruzione `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` eseguendo una query sulle DMV.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-122">The following example collects the query plan for the statement `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` by querying dynamic management views.</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%';  
GO  
```  
  
### <a name="step-2-create-the-plan-guide-to-force-the-plan"></a><span data-ttu-id="a6cb2-123">Passaggio 2: Creazione della guida di piano per l'utilizzo forzato del piano</span><span class="sxs-lookup"><span data-stu-id="a6cb2-123">Step 2: Create the Plan Guide to Force the Plan</span></span>  
 <span data-ttu-id="a6cb2-124">Utilizzando nella guida di piano il piano di query in formato XML ottenuto con uno dei metodi descritti in precedenza, copiare e incollare il piano di query come valore letterale stringa nell'hint per la query USE PLAN specificato nella clausola OPTION di sp_create_plan_guide.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-124">Using the XML-formatted query plan (obtained by any of the methods previously described) in the plan guide, copy and paste the query plan as a string literal inside the USE PLAN query hint specified in the OPTION clause of sp_create_plan_guide.</span></span>  
  
 <span data-ttu-id="a6cb2-125">All'interno del piano XML, aggiungere una seconda virgoletta ai caratteri di escape (') visualizzati nel piano prima di creare la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-125">Within the XML plan itself, escape quotation marks (') that appear in the plan with a second quotation mark before creating the plan guide.</span></span> <span data-ttu-id="a6cb2-126">Ad esempio, per un piano che contiene `WHERE A.varchar = 'This is a string'` è necessario utilizzare i caratteri di escape modificando il codice in `WHERE A.varchar = ''This is a string''`.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-126">For example, a plan that contains `WHERE A.varchar = 'This is a string'` must be escaped by modifying the code to `WHERE A.varchar = ''This is a string''`.</span></span>  
  
 <span data-ttu-id="a6cb2-127">Nell'esempio seguente viene creata una guida di piano per il piano di query raccolto nel passaggio 1 e viene inserito Showplan XML per la query nel parametro `@hints`.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-127">The following example creates a plan guide for the query plan collected in step 1 and inserts the XML Showplan for the query in the `@hints` parameter.</span></span> <span data-ttu-id="a6cb2-128">Per brevità, nell'esempio viene incluso solo l'output Showplan parziale.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-128">For brevity, only partial Showplan output is included in the example.</span></span>  
  
```  
EXECUTE sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',  
@type = N'SQL',  
@module_or_batch = NULL,  
@params = NULL,  
@hints = N'OPTION(USE PLAN N''<ShowPlanXML xmlns=''''https://schemas.microsoft.com/sqlserver/2004/07/showplan''''   
    Version=''''0.5'''' Build=''''9.00.1116''''>  
    <BatchSequence><Batch><Statements><StmtSimple>  
    ...  
    </StmtSimple></Statements></Batch>  
    </BatchSequence></ShowPlanXML>'')';  
GO  
```  
  
### <a name="step-3-verify-that-the-plan-guide-is-applied-to-the-query"></a><span data-ttu-id="a6cb2-129">Passaggio 3: Verifica dell'applicazione della guida di piano alla query</span><span class="sxs-lookup"><span data-stu-id="a6cb2-129">Step 3: Verify That the Plan Guide Is Applied to the Query</span></span>  
 <span data-ttu-id="a6cb2-130">Eseguire nuovamente la query ed esaminare il piano di query prodotto.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-130">Run the query again and examine the query plan that is produced.</span></span> <span data-ttu-id="a6cb2-131">Verificare che il piano corrisponda a quello di cui specificato nella guida.</span><span class="sxs-lookup"><span data-stu-id="a6cb2-131">You should see that the plan matches the one that you specified in the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6cb2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6cb2-132">See Also</span></span>  
 <span data-ttu-id="a6cb2-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6cb2-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="a6cb2-134">[Hint di query &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="a6cb2-134">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="a6cb2-135">Guide di piano</span><span class="sxs-lookup"><span data-stu-id="a6cb2-135">Plan Guides</span></span>](../../relational-databases/performance/plan-guides.md)  
  
  
