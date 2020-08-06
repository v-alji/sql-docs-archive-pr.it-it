---
title: Creare una guida di piano per le query con parametri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- parameterized queries, plan guides for
- plan guides [SQL Server], parameterized queries
ms.assetid: b532ae16-66e7-4641-9bc8-b0d805853477
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 565610826f704274724ea05d821205a5b3391060
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637822"
---
# <a name="create-a-plan-guide-for-parameterized-queries"></a><span data-ttu-id="f413b-102">Creare una guida di piano per le query con parametri</span><span class="sxs-lookup"><span data-stu-id="f413b-102">Create a Plan Guide for Parameterized Queries</span></span>
  <span data-ttu-id="f413b-103">Una guida di piano di tipo TEMPLATE corrisponde alle query autonome con parametrizzazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="f413b-103">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span>  
  
 <span data-ttu-id="f413b-104">Nel seguente esempio viene creata una guida di piano corrispondente a qualsiasi query che parametrizza un formato specifico e forza in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l'esecuzione della parametrizzazione della query.</span><span class="sxs-lookup"><span data-stu-id="f413b-104">The following example creates a plan guide that matches any query that parameterizes to a specified form, and directs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to force parameterization of the query.</span></span> <span data-ttu-id="f413b-105">Le due query seguenti sono equivalenti a livello sintattico. L'unica differenza risiede nei relativi valori letterali costanti.</span><span class="sxs-lookup"><span data-stu-id="f413b-105">The following two queries are syntactically equivalent, but differ only in their constant literal values.</span></span>  
  
```  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45639;  
  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45640;  
```  
  
 <span data-ttu-id="f413b-106">Di seguito è riportata la guida di piano nel formato con parametri della query:</span><span class="sxs-lookup"><span data-stu-id="f413b-106">Here is the plan guide on the parameterized form of the query:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'TemplateGuide1',  
    @stmt = N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
              INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
                  ON h.SalesOrderID = d.SalesOrderID  
              WHERE h.SalesOrderID = @0',  
    @type = N'TEMPLATE',  
    @module_or_batch = NULL,  
    @params = N'@0 int',  
    @hints = N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="f413b-107">Nell'esempio precedente il valore del parametro `@stmt` corrisponde al formato con parametri della query.</span><span class="sxs-lookup"><span data-stu-id="f413b-107">In the previous example, the value for the `@stmt` parameter is the parameterized form of the query.</span></span> <span data-ttu-id="f413b-108">L'unico modo affidabile per ottenere questo valore da usare in sp_create_plan_guide è usare la stored procedure di sistema [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f413b-108">The only reliable way to obtain this value for use in sp_create_plan_guide is to use the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span> <span data-ttu-id="f413b-109">Lo script seguente può essere utilizzato sia per ottenere la query con parametri che per creare una guida di piano in base a essa.</span><span class="sxs-lookup"><span data-stu-id="f413b-109">The following script can be used both to obtain the parameterized query and then create a plan guide on it.</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
      INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
          ON h.SalesOrderID = d.SalesOrderID  
      WHERE h.SalesOrderID = 45639;',  
    @stmt OUTPUT,   
    @params OUTPUT  
EXEC sp_create_plan_guide N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f413b-110">Il valore letterale costante nel parametro `@stmt` passato a `sp_get_query_template` potrebbe interessare il tipo di dati scelto per il parametro che sostituisce il valore letterale.</span><span class="sxs-lookup"><span data-stu-id="f413b-110">The value of the constant literals in the `@stmt` parameter passed to `sp_get_query_template` might affect the data type that is chosen for the parameter that replaces the literal.</span></span> <span data-ttu-id="f413b-111">Ciò potrebbe avere ripercussioni sulla corrispondenza eseguita in base alla guida di piano.</span><span class="sxs-lookup"><span data-stu-id="f413b-111">This will affect plan guide matching.</span></span> <span data-ttu-id="f413b-112">Potrebbe essere necessario creare più guide di piano per gestire intervalli di valori dei parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="f413b-112">You may have to create more than one plan guide to handle different parameter value ranges.</span></span>  
  
 <span data-ttu-id="f413b-113">Le guide di piano di tipo TEMPLATE possono essere utilizzate con le guide di piano di tipo SQL.</span><span class="sxs-lookup"><span data-stu-id="f413b-113">You can also use TEMPLATE plan guides together with SQL plan guides.</span></span> <span data-ttu-id="f413b-114">Ad esempio, è possibile creare una guida di piano di tipo TEMPLATE per assicurarsi che una classe di query venga sottoposta a parametrizzazione</span><span class="sxs-lookup"><span data-stu-id="f413b-114">For example, you can create a TEMPLATE plan guide to make sure that a class of queries is parameterized.</span></span> <span data-ttu-id="f413b-115">È possibile creare una guida di piano di tipo SQL sulla query con parametri.</span><span class="sxs-lookup"><span data-stu-id="f413b-115">You can then create an SQL plan guide on the parameterized form of that query.</span></span>  
  
  
