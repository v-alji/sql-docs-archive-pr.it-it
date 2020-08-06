---
title: Specificare il comportamento di parametrizzazione delle query tramite guide di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- PARAMETERIZATION FORCED option
- PARAMETERIZATION option
- PARAMETERIZATION SIMPLE option
- parameterization [SQL Server]
- overriding parameterization behavior
- plan guides [SQL Server], parameterization
- parameterized queries [SQL Server]
ms.assetid: f0f738ff-2819-4675-a8c8-1eb6c210a7e6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f595b9f0e0a6d7bceffc5cb283c60b6f40e025b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637814"
---
# <a name="specify-query-parameterization-behavior-by-using-plan-guides"></a><span data-ttu-id="e6e47-102">Definizione delle funzionalità di parametrizzazione delle query tramite guide di piano</span><span class="sxs-lookup"><span data-stu-id="e6e47-102">Specify Query Parameterization Behavior by Using Plan Guides</span></span>
  <span data-ttu-id="e6e47-103">Quando l'opzione di database PARAMETERIZATION è impostata su SIMPLE, Query Optimizer di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può scegliere di parametrizzare le query,</span><span class="sxs-lookup"><span data-stu-id="e6e47-103">When the PARAMETERIZATION database option is set to SIMPLE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer may choose to parameterize the queries.</span></span> <span data-ttu-id="e6e47-104">ovvero di sostituire con parametri i valori letterali contenuti in una query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-104">This means that any literal values that are contained in a query are substituted with parameters.</span></span> <span data-ttu-id="e6e47-105">Tale processo viene chiamato parametrizzazione semplice.</span><span class="sxs-lookup"><span data-stu-id="e6e47-105">This process is referred to as simple parameterization.</span></span> <span data-ttu-id="e6e47-106">Quando è attiva una parametrizzazione di tipo SIMPLE, non è possibile distinguere le query con parametri da quelle senza parametri.</span><span class="sxs-lookup"><span data-stu-id="e6e47-106">When SIMPLE parameterization is in effect, you cannot control which queries are parameterized and which queries are not.</span></span> <span data-ttu-id="e6e47-107">È tuttavia possibile specificare che devono essere parametrizzate tutte le query di un database impostando l'opzione di database PARAMETERIZATION su FORCED.</span><span class="sxs-lookup"><span data-stu-id="e6e47-107">However, you can specify that all queries in a database be parameterized by setting the PARAMETERIZATION database option to FORCED.</span></span> <span data-ttu-id="e6e47-108">Tale processo viene chiamato parametrizzazione forzata.</span><span class="sxs-lookup"><span data-stu-id="e6e47-108">This process is referred to as forced parameterization.</span></span>  
  
 <span data-ttu-id="e6e47-109">È possibile sostituire le funzionalità di parametrizzazione di un database nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6e47-109">You can override the parameterization behavior of a database by using plan guides in the following ways:</span></span>  
  
-   <span data-ttu-id="e6e47-110">Quando l'opzione di database PARAMETERIZATION è impostata su SIMPLE, è possibile specificare che la parametrizzazione forzata venga tentata su una determinata classe di query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-110">When the PARAMETERIZATION database option is set to SIMPLE, you can specify that forced parameterization is attempted on a certain class of queries.</span></span> <span data-ttu-id="e6e47-111">A tale scopo, è necessario creare una guida di piano TEMPLATE nel formato con parametri della query e specificare l'hint per la query PARAMETERIZATION FORCED nella stored procedure [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e6e47-111">You do this by creating a TEMPLATE plan guide on the parameterized form of the query, and specifying the PARAMETERIZATION FORCED query hint in the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure.</span></span> <span data-ttu-id="e6e47-112">È possibile considerare questo tipo di guida di piano come uno strumento per abilitare la parametrizzazione forzata solo su una determinata classe di query, anziché su tutte le query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-112">You can consider this kind of plan guide as a way to enable forced parameterization only on a certain class of queries, instead of all queries.</span></span>  
  
-   <span data-ttu-id="e6e47-113">Quando l'opzione di database PARAMETERIZATION è impostata su FORCED, è possibile specificare che venga tentata solo la parametrizzazione semplice, anziché forzata, su una determinata classe di query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-113">When the PARAMETERIZATION database option is set to FORCED, you can specify that for a certain class of queries, only simple parameterization is attempted, not forced parameterization.</span></span> <span data-ttu-id="e6e47-114">A tale scopo, è necessario creare una guida di piano TEMPLATE nel formato di query force-parametrized e specificare l'hint per la query PARAMETERIZATION SIMPLE nella stored procedure **sp_create_plan_guide**.</span><span class="sxs-lookup"><span data-stu-id="e6e47-114">You do this by creating a TEMPLATE plan guide on the force-parameterized form of the query, and specifying the PARAMETERIZATION SIMPLE query hint in **sp_create_plan_guide**.</span></span>  
  
 <span data-ttu-id="e6e47-115">Si consideri la query seguente sul database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="e6e47-115">Consider the following query on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT pi.ProductID, SUM(pi.Quantity) AS Total  
FROM Production.ProductModel AS pm   
    INNER JOIN Production.ProductInventory AS pi   
        ON pm.ProductModelID = pi.ProductID   
WHERE pi.ProductID = 101   
GROUP BY pi.ProductID, pi.Quantity HAVING SUM(pi.Quantity) > 50;  
```  
  
 <span data-ttu-id="e6e47-116">L'amministratore di database ha deciso di non abilitare la parametrizzazione forzata su tutte le query del database.</span><span class="sxs-lookup"><span data-stu-id="e6e47-116">As a database administrator, you have determined that you do not want to enable forced parameterization on all queries in the database.</span></span> <span data-ttu-id="e6e47-117">Tuttavia, l'amministratore desidera evitare i costi di compilazione relativi a tutte le query sintatticamente equivalenti alla query precedente ma che si differenziano solo per i relativi valori letterali costanti.</span><span class="sxs-lookup"><span data-stu-id="e6e47-117">However, you do want to avoid compilation costs on all queries that are syntactically equivalent to the previous query, but differ only in their constant literal values.</span></span> <span data-ttu-id="e6e47-118">In altre parole, desidera che la query venga parametrizzata in modo da riutilizzare un piano per questo tipo di query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-118">In other words, you want the query to be parameterized so that a query plan for this kind of query is reused.</span></span> <span data-ttu-id="e6e47-119">In tal caso, è necessario completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6e47-119">In this case, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="e6e47-120">Recuperare il formato con parametri della query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-120">Retrieve the parameterized form of the query.</span></span> <span data-ttu-id="e6e47-121">L'unico metodo affidabile per ottenere questo valore da usare in **sp_create_plan_guide** consiste nell'uso della stored procedure di sistema [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e6e47-121">The only safe way to obtain this value for use in **sp_create_plan_guide** is by using the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span>  
  
2.  <span data-ttu-id="e6e47-122">Creare la guida di piano nel formato con parametri della query, specificando l'hint per la query PARAMETERIZATION FORCED.</span><span class="sxs-lookup"><span data-stu-id="e6e47-122">Create the plan guide on the parameterized form of the query, specifying the PARAMETERIZATION FORCED query hint.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e6e47-123">Nell'ambito della parametrizzazione di una query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assegna un tipo di dati ai parametri che sostituiscono i valori letterali, in base al valore e alle dimensioni del valore letterale specifico.</span><span class="sxs-lookup"><span data-stu-id="e6e47-123">As part of parameterizing a query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns a data type to the parameters that replace the literal values, depending on the value and size of the literal.</span></span> <span data-ttu-id="e6e47-124">Lo stesso processo si verifica nel valore dei valori letterali costanti passati al **@stmt** parametro di output di **sp_get_query_template**.</span><span class="sxs-lookup"><span data-stu-id="e6e47-124">The same process occurs to the value of the constant literals passed to the **@stmt** output parameter of **sp_get_query_template**.</span></span> <span data-ttu-id="e6e47-125">Poiché il tipo di dati specificato nell' **@params** argomento di **sp_create_plan_guide** deve corrispondere a quello della query in quanto è parametrizzato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , potrebbe essere necessario creare più guide di piano per coprire l'intervallo completo di possibili valori di parametro per la query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-125">Because the data type specified in the **@params** argument of **sp_create_plan_guide** must match that of the query as it is parameterized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you may have to create more than one plan guide to cover the complete range of possible parameter values for the query.</span></span>  
  
 <span data-ttu-id="e6e47-126">Lo script seguente può essere utilizzato sia per ottenere la query con parametri che per creare in seguito una guida di piano basata su tale query.</span><span class="sxs-lookup"><span data-stu-id="e6e47-126">The following script can be used both to obtain the parameterized query and then create a plan guide on it:</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT pi.ProductID, SUM(pi.Quantity) AS Total   
      FROM Production.ProductModel AS pm   
      INNER JOIN Production.ProductInventory AS pi ON pm.ProductModelID = pi.ProductID   
      WHERE pi.ProductID = 101   
      GROUP BY pi.ProductID, pi.Quantity   
      HAVING sum(pi.Quantity) > 50',  
    @stmt OUTPUT,   
    @params OUTPUT;  
EXEC sp_create_plan_guide   
    N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="e6e47-127">Analogamente, in un database in cui è già abilitata la parametrizzazione forzata è possibile verificare che la query di esempio e le altre sintatticamente equivalenti, tranne per i relativi valori letterali costanti, siano con parametri in conformità alle regole della parametrizzazione semplice.</span><span class="sxs-lookup"><span data-stu-id="e6e47-127">Similarly, in a database in which forced parameterization is already enabled, you can make sure that the sample query, and others that are syntactically equivalent, except for their constant literal values, are parameterized according to the rules of simple parameterization.</span></span> <span data-ttu-id="e6e47-128">A tale scopo, nella clausola OPTION è necessario specificare PARAMETERIZATION SIMPLE anziché PARAMETERIZATION FORCED.</span><span class="sxs-lookup"><span data-stu-id="e6e47-128">To do this, specify PARAMETERIZATION SIMPLE instead of PARAMETERIZATION FORCED in the OPTION clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6e47-129">Le guide di piano TEMPLATE definiscono la corrispondenza tra le istruzioni e le query inviate in batch costituite da una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="e6e47-129">TEMPLATE plan guides match statements to queries submitted in batches that consist of a single statement only.</span></span> <span data-ttu-id="e6e47-130">Le istruzioni all'interno di batch costituiti da più istruzioni non sono idonee per la corrispondenza definita dalle guide di piano TEMPLATE.</span><span class="sxs-lookup"><span data-stu-id="e6e47-130">Statements inside multistatement batches are not eligible to be matched by TEMPLATE plan guides.</span></span>  
  
  
