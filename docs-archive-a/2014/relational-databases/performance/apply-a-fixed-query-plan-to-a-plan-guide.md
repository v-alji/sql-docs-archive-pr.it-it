---
title: Applicare un piano di query fisso a una guida di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: bbf401f9-af7c-48e7-8a43-bf25e8af2fd7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 318955c4d0550e311873d8b4a6f79f72e04ac8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713067"
---
# <a name="apply-a-fixed-query-plan-to-a-plan-guide"></a><span data-ttu-id="906a9-102">Applicare un piano di query fisso a una guida di piano</span><span class="sxs-lookup"><span data-stu-id="906a9-102">Apply a Fixed Query Plan to a Plan Guide</span></span>
  <span data-ttu-id="906a9-103">È possibile applicare un piano di query fisso a una guida di piano di tipo OBJECT o SQL.</span><span class="sxs-lookup"><span data-stu-id="906a9-103">You can apply a fixed query plan to a plan guide of type OBJECT or SQL.</span></span> <span data-ttu-id="906a9-104">Le guide di piano che applicano un piano di query fisso risultano utili quando per una specifica query esiste un piano di esecuzione che offre prestazioni migliori rispetto a quello selezionato da Query Optimizer.</span><span class="sxs-lookup"><span data-stu-id="906a9-104">Plan guides that apply a fixed query plan are useful when you know about an existing execution plan that performs better than the one selected by the optimizer for a particular query.</span></span>  
  
 <span data-ttu-id="906a9-105">Nell'esempio seguente viene creata una guida di piano per una semplice istruzione SQL ad hoc.</span><span class="sxs-lookup"><span data-stu-id="906a9-105">The following example creates a plan guide for a simple ad hoc SQL statement.</span></span> <span data-ttu-id="906a9-106">Il piano di query desiderato per questa istruzione è fornito nella guida di piano specificando lo Showplan XML per la query direttamente nel parametro `@hints` .</span><span class="sxs-lookup"><span data-stu-id="906a9-106">The desired query plan for this statement is provided in the plan guide by specifying the XML Showplan for the query directly in the `@hints` parameter.</span></span> <span data-ttu-id="906a9-107">Viene innanzitutto eseguita l'istruzione SQL per generare un piano nella cache dei piani.</span><span class="sxs-lookup"><span data-stu-id="906a9-107">The example first executes the SQL statement to generate a plan in the plan cache.</span></span> <span data-ttu-id="906a9-108">Ai fini di questo esempio, si presuppone che il piano generato sia il piano desiderato, senza che sia richiesta alcuna ottimizzazione aggiuntiva della query.</span><span class="sxs-lookup"><span data-stu-id="906a9-108">For the purposes of this example, it is assumed that the generated plan is the desired plan and no additional query tuning is required.</span></span> <span data-ttu-id="906a9-109">Lo Showplan XML per la query si ottiene eseguendo una query sulle viste a gestione dinamica `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`e `sys.dm_exec_text_query_plan` e assegnandolo alla variabile `@xml_showplan` .</span><span class="sxs-lookup"><span data-stu-id="906a9-109">The XML Showplan for the query is obtained by querying the `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`, and `sys.dm_exec_text_query_plan` dynamic management views and is assigned to the `@xml_showplan` variable.</span></span> <span data-ttu-id="906a9-110">La variabile `@xml_showplan` passa quindi all'istruzione `sp_create_plan_guide` nel parametro `@hints` .</span><span class="sxs-lookup"><span data-stu-id="906a9-110">The `@xml_showplan` variable is then passed to the `sp_create_plan_guide` statement in the `@hints` parameter.</span></span> <span data-ttu-id="906a9-111">In alternativa, è possibile creare una guida di piano da un piano di query nella cache dei piani usando la stored procedure [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="906a9-111">Or, you can create a plan guide from a query plan in the plan cache by using the [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;  
GO  
DECLARE @xml_showplan nvarchar(max);  
SET @xml_showplan = (SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%');  
  
EXEC sp_create_plan_guide   
    @name = N'Guide1_from_XML_showplan',   
    @stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',   
    @type = N'SQL',  
    @module_or_batch = NULL,   
    @params = NULL,   
    @hints = @xml_showplan;  
GO  
```  
  
  
