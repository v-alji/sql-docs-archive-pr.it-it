---
title: Implementazione dell'operatore OR in stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2528e74-2b1c-48cb-861b-c4e57b51ac35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ed762e062cbc6831eb46784ef71fc7889850676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718713"
---
# <a name="implementing-the-or-operator-in-natively-compiled-stored-procedures"></a><span data-ttu-id="93dc3-102">Implementazione dell'operatore OR in stored procedure compilate in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="93dc3-102">Implementing the OR Operator in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="93dc3-103">Gli operatori OR non sono supportati nei predicati di query in stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="93dc3-103">OR operators are not supported in query predicates in natively compiled stored procedures.</span></span> <span data-ttu-id="93dc3-104">Dal momento che anche gli operatori NOT non sono supportati nei predicati di query in stored procedure compilate in modo nativo, gli effetti degli operatori OR non possono essere simulati da soli tramite l'utilizzo degli operatori logici equivalenti.</span><span class="sxs-lookup"><span data-stu-id="93dc3-104">Because NOT operators are also not supported in query predicates in natively compiled stored procedures, the effects of OR operators cannot be simulated through the use of equivalent logical operators alone.</span></span> <span data-ttu-id="93dc3-105">Tuttavia, gli effetti di un operatore OR possono essere simulati con variabili di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="93dc3-105">However, the effects of an OR operator may be simulated with memory-optimized table variables.</span></span>  
  
## <a name="or-operator-in-where-clause"></a><span data-ttu-id="93dc3-106">Operatore OR nella clausola WHERE</span><span class="sxs-lookup"><span data-stu-id="93dc3-106">OR Operator in WHERE Clause</span></span>  
 <span data-ttu-id="93dc3-107">Se si dispone di un operatore OR in una clausola WHERE, è possibile utilizzare l'approccio seguente per simularne il comportamento:</span><span class="sxs-lookup"><span data-stu-id="93dc3-107">If you have an OR operator in a WHERE clause, you can use the following approach to simulate its behavior:</span></span>  
  
1.  <span data-ttu-id="93dc3-108">Creare una variabile di tabella ottimizzata per la memoria con lo schema appropriato.</span><span class="sxs-lookup"><span data-stu-id="93dc3-108">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="93dc3-109">Per questa operazione è necessario un tipo di tabella ottimizzata per la memoria predefinito.</span><span class="sxs-lookup"><span data-stu-id="93dc3-109">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="93dc3-110">A partire dall'operatore OR di livello principale, separare la clausola WHERE in due parti in base ai predicati uniti dall'operatore OR.</span><span class="sxs-lookup"><span data-stu-id="93dc3-110">Starting with the top level OR operator, separate the WHERE clause into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="93dc3-111">Se si dispone di più operatori OR nella clausola WHERE, potrebbe essere necessario eseguire questa operazione più volte.</span><span class="sxs-lookup"><span data-stu-id="93dc3-111">If you have more than one OR operator in a WHERE clause, you may need to do this more than once.</span></span> <span data-ttu-id="93dc3-112">Ripetere questo passaggio finché non rimane alcun operatore OR.</span><span class="sxs-lookup"><span data-stu-id="93dc3-112">Repeat this step until no OR operators remain.</span></span> <span data-ttu-id="93dc3-113">Ad esempio, se si dispone del predicato seguente:</span><span class="sxs-lookup"><span data-stu-id="93dc3-113">For example, if you have the following predicate:</span></span>  
  
    ```  
    pred1 OR (pred2 AND (pred3 OR pred4)) OR (pred5 AND pred6)  
    ```  
  
     <span data-ttu-id="93dc3-114">Dopo questo passaggio, si dovrebbe disporre dei predicati seguenti:</span><span class="sxs-lookup"><span data-stu-id="93dc3-114">After this step, you should have the following predicates:</span></span>  
  
    ```  
    pred1  
    pred5 AND pred6  
    pred2 AND pred3  
    pred2 AND pred4  
    ```  
  
3.  <span data-ttu-id="93dc3-115">Eseguire una query con ognuna delle due parti presenti nel Passaggio 2 come predicato.</span><span class="sxs-lookup"><span data-stu-id="93dc3-115">Execute a query with each of the two parts found in Step 2 as the predicate.</span></span> <span data-ttu-id="93dc3-116">Incollare il risultato di ogni query nella variabile di tabella ottimizzata per la memoria creata nel Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="93dc3-116">Insert the result for each query into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="93dc3-117">Se necessario, rimuovere i duplicati dalla variabile di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="93dc3-117">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="93dc3-118">Utilizzare il contenuto della variabile di tabella ottimizzata per la memoria come risultato della query.</span><span class="sxs-lookup"><span data-stu-id="93dc3-118">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="93dc3-119">Nell'esempio seguente vengono utilizzate tabelle del database AdventureWorks2012 aggiornate per [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93dc3-119">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="93dc3-120">Per scaricare i file per questo esempio, vai ai [database AdventureWorks-2012, 2008R2 e 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="93dc3-120">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="93dc3-121">Per applicare l' [!INCLUDE[hek_2](../includes/hek-2-md.md)] esempio di codice a AdventureWorks2012, passare all' [esempio di OLTP In memoria SQL Server 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="93dc3-121">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="93dc3-122">Aggiungere la seguente stored procedure al database.</span><span class="sxs-lookup"><span data-stu-id="93dc3-122">Add the following stored procedure to the database.</span></span> <span data-ttu-id="93dc3-123">Questa stored procedure verrà convertita per utilizzare la compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="93dc3-123">We will convert this stored procedure to use native compilation.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_ondisk  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
AS BEGIN  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  WHERE  s.SalesOrderId = @SalesOrderId  
      OR s.SalesOrderDetailId = @SalesOrderDetailId  
      OR s.CarrierTrackingNumber = @CarrierTrackingNumber  
      OR s.ProductID = @ProductId  
      OR (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
END  
GO  
```  
  
 <span data-ttu-id="93dc3-124">Dopo la conversione, lo schema della stored procedure e della tabella sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="93dc3-124">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesOrderDetailType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailTempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  recordcount int not null  
  INDEX ix_fuzzySearchSalesOrderDetailTempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_inmem  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.fuzzySearchSalesOrderDetailType  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderId = @SalesOrderId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderDetailId = @SalesOrderDetailId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.CarrierTrackingNumber COLLATE Latin1_General_BIN2 = @CarrierTrackingNumber COLLATE Latin1_General_BIN2   
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.ProductID = @ProductId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
  
  -- After the above statements, there will be duplicates inside @retValue  
  -- Delete the duplicates from @retValue  
  DECLARE @duplicates Sales.fuzzySearchSalesOrderDetailTempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, recordcount)   
  SELECT SalesOrderId, SalesOrderDetailId, COUNT(*) AS recordCount  
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId  
  
  -- Now we have one row per pair  
  -- clear and rebuild the result set  
  DELETE FROM @retValue  
  
  INSERT INTO @retValue  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates d ON s.SalesOrderId = d.SalesOrderId AND s.SalesOrderDetailId = d.SalesOrderDetailId  
  
  -- After this every pair of (SalesOrderId, SalesOrderDetailId) in @retValue should be unique.  
  SELECT SalesorderId, SalesOrderDetailId, ModifiedDate FROM @retValue  
END  
GO  
```  
  
## <a name="or-operator-in-join-condition"></a><span data-ttu-id="93dc3-125">Operatore OR nella condizione JOIN</span><span class="sxs-lookup"><span data-stu-id="93dc3-125">OR Operator in JOIN Condition</span></span>  
 <span data-ttu-id="93dc3-126">Se si dispone di un operatore OR in una condizione JOIN di un'istruzione SELECT, è possibile utilizzare l'approccio seguente per simularne il comportamento.</span><span class="sxs-lookup"><span data-stu-id="93dc3-126">If you have an OR operator in a JOIN condition of a SELECT statement, you may use the following approach to simulate its behavior.</span></span> <span data-ttu-id="93dc3-127">Se si dispone di più operatori OR in una condizione JOIN o di più condizioni JOIN con operatori OR, potrebbe essere necessario eseguire questa operazione più volte.</span><span class="sxs-lookup"><span data-stu-id="93dc3-127">If you have more than one OR operator in a JOIN condition or you have multiple JOIN condition with OR operators, you may need to do this more than once.</span></span>  
  
 <span data-ttu-id="93dc3-128">Se si dispone di condizioni OUTER JOIN, è possibile combinare questa soluzione alternativa con quella per le condizioni OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="93dc3-128">If you have OUTER JOIN conditions, you may combine this workaround with the workaround for OUTER JOIN conditions.</span></span>  
  
1.  <span data-ttu-id="93dc3-129">Creare una variabile di tabella ottimizzata per la memoria con lo schema appropriato.</span><span class="sxs-lookup"><span data-stu-id="93dc3-129">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="93dc3-130">Per questa operazione è necessario un tipo di tabella ottimizzata per la memoria predefinito.</span><span class="sxs-lookup"><span data-stu-id="93dc3-130">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="93dc3-131">Separare il predicato nella condizione JOIN in due parti in base ai predicati uniti dall'operatore OR.</span><span class="sxs-lookup"><span data-stu-id="93dc3-131">Separate the predicate in the JOIN condition into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="93dc3-132">Se si dispone di più condizioni JOIN, potrebbe essere necessario eseguire questa operazione per ogni condizione JOIN, quindi creare un set di combinazioni dei frammenti risultanti.</span><span class="sxs-lookup"><span data-stu-id="93dc3-132">If you have multiple JOIN conditions, you may need to do this for each JOIN condition and then create a set of combinations of the resulting fragments.</span></span> <span data-ttu-id="93dc3-133">Ad esempio, se si dispone di tre condizioni JOIN con un operatore OR in ogni condizione JOIN, si potrebbe disporre di 2x2x2=8 predicati.</span><span class="sxs-lookup"><span data-stu-id="93dc3-133">For example, if you have three JOIN conditions with one OR operator in each JOIN condition, you may have 2x2x2=8 predicates.</span></span>  
  
3.  <span data-ttu-id="93dc3-134">Per ogni predicato prodotto dal Passaggio 2, creare una query tramite cui verrà inserito il relativo risultato nella variabile di tabella ottimizzata per la memoria creata nel Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="93dc3-134">For each predicate produced by Step 2, create a query that will insert its result into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="93dc3-135">Se necessario, rimuovere i duplicati dalla variabile di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="93dc3-135">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="93dc3-136">Utilizzare il contenuto della variabile di tabella ottimizzata per la memoria come risultato della query.</span><span class="sxs-lookup"><span data-stu-id="93dc3-136">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="93dc3-137">Nell'esempio seguente vengono utilizzate tabelle del database AdventureWorks2012 aggiornate per [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93dc3-137">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="93dc3-138">Per scaricare i file per questo esempio, vai ai [database AdventureWorks-2012, 2008R2 e 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="93dc3-138">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="93dc3-139">Per applicare l' [!INCLUDE[hek_2](../includes/hek-2-md.md)] esempio di codice a AdventureWorks2012, passare all' [esempio di OLTP In memoria SQL Server 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="93dc3-139">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="93dc3-140">Aggiungere la seguente stored procedure al database.</span><span class="sxs-lookup"><span data-stu-id="93dc3-140">Add the following stored procedure to the database.</span></span> <span data-ttu-id="93dc3-141">Questa stored procedure verrà convertita per utilizzare la compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="93dc3-141">We will convert this stored procedure to use native compilation.</span></span> <span data-ttu-id="93dc3-142">In questo esempio vengono utilizzate le condizioni INNER JOIN.</span><span class="sxs-lookup"><span data-stu-id="93dc3-142">This sample uses INNER JOIN conditions.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_ondisk  
  @SpecialOfferId int  
AS BEGIN  
  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  JOIN Sales.SpecialOffer_onDisk offer   
    ON s.SpecialOfferID = offer.SpecialOfferID   
    OR s.ProductID IN (SELECT ProductId FROM Sales.SpecialOfferProduct sop WHERE sop.SpecialOfferID = @SpecialOfferId)  
END  
```  
  
 <span data-ttu-id="93dc3-143">Dopo la conversione, lo schema della stored procedure e della tabella sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="93dc3-143">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_Type AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesSpecialOffers_Type NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_TempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  recordcount int null  
  INDEX ix_fuzzySearchSalesSpecialOffers_TempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_inmem  
  @SpecialOfferId int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.FuzzySearchSalesSpecialOffers_Type  
  
  -- Find all special offers matching the conditions  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOffer_inmem offer   
    ON s.SpecialOfferID = offer.SpecialOfferID  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOfferProduct_inmem sop   
    ON sop.SpecialOfferId = @SpecialOfferId AND s.ProductID = sop.ProductId  
  
  -- Now we need to remove the duplicates from @matchingSpecialOffers  
  DECLARE @duplicates Sales.fuzzySearchSalesSpecialOffers_TempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, SpecialOfferid, recordcount)  
  SELECT SalesOrderId, SalesOrderDetailId, SpecialOfferId, COUNT(*)   
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId, SpecialOfferId  
  
  -- now there should be no duplicates within @duplicate  
  -- use @duplicate for join.  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates offer   
    ON    s.SalesOrderId = offer.SalesOrderId   
      AND s.SalesOrderDetailId = offer.SalesOrderDetailID   
      AND s.SpecialOfferId = offer.SpecialOfferId  
END  
GO  
```  
  
## <a name="side-effects"></a><span data-ttu-id="93dc3-144">Effetti collaterali</span><span class="sxs-lookup"><span data-stu-id="93dc3-144">Side Effects</span></span>  
 <span data-ttu-id="93dc3-145">Se si dispone di più operatori OR nella clausola WHERE o nella condizione JOIN, il numero di query necessario per eseguire la simulazione del comportamento può aumentare in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="93dc3-145">If you have more than one OR operator in the WHERE clause or JOIN condition, the number of queries you need to execute to simulate the behavior may increase exponentially.</span></span> <span data-ttu-id="93dc3-146">Ciò può rallentare le prestazioni delle query e aumentare l'utilizzo della memoria a causa della necessità di utilizzare variabili di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="93dc3-146">This may slow down query performance and may increase memory usage due to the need to use memory-optimized table variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93dc3-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93dc3-147">See Also</span></span>  
 [<span data-ttu-id="93dc3-148">Problemi di migrazione relativi alle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="93dc3-148">Migration Issues for Natively Compiled Stored Procedures</span></span>](../relational-databases/in-memory-oltp/migration-issues-for-natively-compiled-stored-procedures.md)  
  
