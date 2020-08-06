---
title: Creare funzioni definite dall'utente (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- SCHEMABINDING clause
- schema-bound functions [SQL Server]
- user-defined functions [SQL Server], creating
- CREATE FUNCTION statement
- valid statements [SQL Server]
ms.assetid: f0d5dd10-73fd-4e05-9177-07f56552bdf7
author: rothja
ms.author: jroth
ms.openlocfilehash: 790fa1b969f933890e050311173fcde3f12c37ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637120"
---
# <a name="create-user-defined-functions-database-engine"></a><span data-ttu-id="f10e0-102">Creazione di funzioni definite dall'utente (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="f10e0-102">Create User-defined Functions (Database Engine)</span></span>
  <span data-ttu-id="f10e0-103">In questo argomento viene descritto come creare una funzione definita dall'utente in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f10e0-103">This topic describes how to create a user-defined function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f10e0-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f10e0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f10e0-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f10e0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f10e0-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f10e0-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f10e0-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f10e0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f10e0-108">**Per creare una funzione definita dall'utente:**</span><span class="sxs-lookup"><span data-stu-id="f10e0-108">**To create a user-defined function:**</span></span>  
  
     [<span data-ttu-id="f10e0-109">Creare una funzione scalare</span><span class="sxs-lookup"><span data-stu-id="f10e0-109">Create a Scalar Function</span></span>](#Scalar)  
  
     [<span data-ttu-id="f10e0-110">Creare una funzione con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="f10e0-110">Create a Table-valued Function</span></span>](#TVF)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f10e0-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f10e0-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f10e0-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f10e0-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f10e0-113">Non è possibile utilizzare funzioni definite dall'utente per eseguire azioni che modificano lo stato del database.</span><span class="sxs-lookup"><span data-stu-id="f10e0-113">User-defined functions cannot be used to perform actions that modify the database state.</span></span>  
  
-   <span data-ttu-id="f10e0-114">Le funzioni definite dall'utente non possono contenere una clausola OUTPUT INTO che ha una tabella come destinazione.</span><span class="sxs-lookup"><span data-stu-id="f10e0-114">User-defined functions cannot contain an OUTPUT INTO clause that has a table as its target.</span></span>  
  
-   <span data-ttu-id="f10e0-115">Tramite le funzioni definite dall'utente non possono essere restituiti più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="f10e0-115">User-defined functions can not return multiple result sets.</span></span> <span data-ttu-id="f10e0-116">Utilizzare una stored procedure se è necessario restituire più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="f10e0-116">Use a stored procedure if you need to return multiple result sets.</span></span>  
  
-   <span data-ttu-id="f10e0-117">In una funzione definita dall'utente la gestione degli errori è limitata.</span><span class="sxs-lookup"><span data-stu-id="f10e0-117">Error handling is restricted in a user-defined function.</span></span> <span data-ttu-id="f10e0-118">Una funzione definita dall'utente non supporta TRY... CATCH, @ERROR o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="f10e0-118">A UDF does not support TRY...CATCH, @ERROR or RAISERROR.</span></span>  
  
-   <span data-ttu-id="f10e0-119">Tramite le funzioni definite dall'utente non è possibile chiamare una stored procedure normale, bensì una estesa.</span><span class="sxs-lookup"><span data-stu-id="f10e0-119">User-defined functions cannot call a stored procedure, but can call an extended stored procedure.</span></span>  
  
-   <span data-ttu-id="f10e0-120">Nelle funzioni definite dall'utente non è possibile utilizzare tabelle temporanee o SQL dinamiche.</span><span class="sxs-lookup"><span data-stu-id="f10e0-120">User-defined functions cannot make use of dynamic SQL or temp tables.</span></span> <span data-ttu-id="f10e0-121">Sono consentite le variabili di tabella.</span><span class="sxs-lookup"><span data-stu-id="f10e0-121">Table variables are allowed.</span></span>  
  
-   <span data-ttu-id="f10e0-122">In una funzione definita dall'utente non sono consentite istruzioni SET.</span><span class="sxs-lookup"><span data-stu-id="f10e0-122">SET statements are not allowed in a user-defined function.</span></span>  
  
-   <span data-ttu-id="f10e0-123">La clausola FOR XML non è consentita</span><span class="sxs-lookup"><span data-stu-id="f10e0-123">The FOR XML clause is not allowed</span></span>  
  
-   <span data-ttu-id="f10e0-124">È possibile nidificare le funzioni definite dall'utente, ovvero una funzione definita dall'utente ne può richiamare un'altra.</span><span class="sxs-lookup"><span data-stu-id="f10e0-124">User-defined functions can be nested; that is, one user-defined function can call another.</span></span> <span data-ttu-id="f10e0-125">Il livello di nidificazione aumenta all'avvio della funzione richiamata e diminuisce al termine dell'esecuzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="f10e0-125">The nesting level is incremented when the called function starts execution, and decremented when the called function finishes execution.</span></span> <span data-ttu-id="f10e0-126">Le funzioni definite dall'utente possono essere nidificate fino a un massimo di 32 livelli.</span><span class="sxs-lookup"><span data-stu-id="f10e0-126">User-defined functions can be nested up to 32 levels.</span></span> <span data-ttu-id="f10e0-127">Se viene superato il livello massimo di nidificazioni, l'intera sequenza di funzioni chiamanti ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f10e0-127">Exceeding the maximum levels of nesting causes the whole calling function chain to fail.</span></span> <span data-ttu-id="f10e0-128">Qualsiasi riferimento al codice gestito presente in una funzione definita dall'utente Transact-SQL viene considerato come un livello nel contesto del limite di 32 livelli di nidificazione.</span><span class="sxs-lookup"><span data-stu-id="f10e0-128">Any reference to managed code from a Transact-SQL user-defined function counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="f10e0-129">I metodi richiamati da codice gestito non vengono inclusi nel conteggio per questo limite.</span><span class="sxs-lookup"><span data-stu-id="f10e0-129">Methods invoked from within managed code do not count against this limit.</span></span>  
  
-   <span data-ttu-id="f10e0-130">Nella definizione di una funzione definita dall'utente Transact-SQL non è possibile includere le istruzioni di Service Broker seguenti:</span><span class="sxs-lookup"><span data-stu-id="f10e0-130">The following Service Broker statements cannot be included in the definition of a Transact-SQL user-defined function:</span></span>  
  
    -   <span data-ttu-id="f10e0-131">BEGIN DIALOG CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="f10e0-131">BEGIN DIALOG CONVERSATION</span></span>  
  
    -   <span data-ttu-id="f10e0-132">END CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="f10e0-132">END CONVERSATION</span></span>  
  
    -   <span data-ttu-id="f10e0-133">GET CONVERSATION GROUP</span><span class="sxs-lookup"><span data-stu-id="f10e0-133">GET CONVERSATION GROUP</span></span>  
  
    -   <span data-ttu-id="f10e0-134">MOVE CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="f10e0-134">MOVE CONVERSATION</span></span>  
  
    -   <span data-ttu-id="f10e0-135">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="f10e0-135">RECEIVE</span></span>  
  
    -   <span data-ttu-id="f10e0-136">SEND</span><span class="sxs-lookup"><span data-stu-id="f10e0-136">SEND</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f10e0-137">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f10e0-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f10e0-138">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f10e0-138">Permissions</span></span>  
 <span data-ttu-id="f10e0-139">È necessario disporre dell'autorizzazione CREATE FUNCTION nel database e dell'autorizzazione ALTER per lo schema in cui la funzione è in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="f10e0-139">Requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span> <span data-ttu-id="f10e0-140">Se per la funzione viene specificato un tipo definito dall'utente, è necessario disporre dell'autorizzazione EXECUTE per tale tipo.</span><span class="sxs-lookup"><span data-stu-id="f10e0-140">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="scalar-functions"></a><a name="Scalar"></a><span data-ttu-id="f10e0-141">Funzioni scalari</span><span class="sxs-lookup"><span data-stu-id="f10e0-141">Scalar Functions</span></span>  
 <span data-ttu-id="f10e0-142">Negli esempi seguenti viene creata una funzione scalare a più istruzioni nel database [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f10e0-142">The following example creates a multistatement scalar function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="f10e0-143">La funzione accetta un valore di input, un valore `ProductID`e restituisce un singolo valore di dati, la quantità aggregata del prodotto specificato nelle scorte.</span><span class="sxs-lookup"><span data-stu-id="f10e0-143">The function takes one input value, a `ProductID`, and returns a single data value, the aggregated quantity of the specified product in inventory.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufnGetInventoryStock', N'FN') IS NOT NULL  
    DROP FUNCTION ufnGetInventoryStock;  
GO  
CREATE FUNCTION dbo.ufnGetInventoryStock(@ProductID int)  
RETURNS int   
AS   
-- Returns the stock level for the product.  
BEGIN  
    DECLARE @ret int;  
    SELECT @ret = SUM(p.Quantity)   
    FROM Production.ProductInventory p   
    WHERE p.ProductID = @ProductID   
        AND p.LocationID = '6';  
     IF (@ret IS NULL)   
        SET @ret = 0;  
    RETURN @ret;  
END;  
GO  
  
```  
  
 <span data-ttu-id="f10e0-144">Nell'esempio seguente viene utilizzata la funzione `ufnGetInventoryStock` per conoscere la quantità di scorte corrente dei prodotti il cui valore `ProductModelID` è compreso tra 75 e 80.</span><span class="sxs-lookup"><span data-stu-id="f10e0-144">The following example uses the `ufnGetInventoryStock` function to return the current inventory quantity for products that have a `ProductModelID` between 75 and 80.</span></span>  
  
```  
SELECT ProductModelID, Name, dbo.ufnGetInventoryStock(ProductID)AS CurrentSupply  
FROM Production.Product  
WHERE ProductModelID BETWEEN 75 and 80;  
  
```  
  
##  <a name="table-valued-functions"></a><a name="TVF"></a><span data-ttu-id="f10e0-145">Funzioni con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="f10e0-145">Table-Valued Functions</span></span>  
 <span data-ttu-id="f10e0-146">Nell'esempio seguente viene creata una funzione inline con valori di tabella nel database [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f10e0-146">The following example creates an inline table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="f10e0-147">La funzione accetta un parametro di input, un ID (punto vendita) cliente e restituisce le colonne `ProductID`, `Name`e l'aggregazione delle vendite per l'anno in corso come valore `YTD Total` per ogni prodotto venduto al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="f10e0-147">The function takes one input parameter, a customer (store) ID, and returns the columns `ProductID`, `Name`, and the aggregate of year-to-date sales as `YTD Total` for each product sold to the store.</span></span>  
  
```  
IF OBJECT_ID (N'Sales.ufn_SalesByStore', N'IF') IS NOT NULL  
    DROP FUNCTION Sales.ufn_SalesByStore;  
GO  
CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
    FROM Production.Product AS P   
    JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
    JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
    JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
    WHERE C.StoreID = @storeid  
    GROUP BY P.ProductID, P.Name  
);  
  
```  
  
 <span data-ttu-id="f10e0-148">Nell'esempio seguente viene richiamata la funzione e viene specificato l'ID cliente 602.</span><span class="sxs-lookup"><span data-stu-id="f10e0-148">The following example invokes the function and specifies customer ID 602.</span></span>  
  
```  
SELECT * FROM Sales.ufn_SalesByStore (602);  
  
```  
  
 <span data-ttu-id="f10e0-149">Nell'esempio seguente viene creata una funzione con valori di tabella nel database [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f10e0-149">The following example creates a table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="f10e0-150">Nella funzione viene accettato un solo parametro di input, un valore `EmployeeID` , e tramite essa viene restituito un elenco di tutti i dipendenti che fanno riferimento direttamente o indirettamente al dipendente specificato.</span><span class="sxs-lookup"><span data-stu-id="f10e0-150">The function takes a single input parameter, an `EmployeeID` and returns a list of all the employees who report to the specified employee directly or indirectly.</span></span> <span data-ttu-id="f10e0-151">La funzione viene quindi richiamata specificando l'ID dipendente 109.</span><span class="sxs-lookup"><span data-stu-id="f10e0-151">The function is then invoked specifying employee ID 109.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufn_FindReports', N'TF') IS NOT NULL  
    DROP FUNCTION dbo.ufn_FindReports;  
GO  
CREATE FUNCTION dbo.ufn_FindReports (@InEmpID INTEGER)  
RETURNS @retFindReports TABLE   
(  
    EmployeeID int primary key NOT NULL,  
    FirstName nvarchar(255) NOT NULL,  
    LastName nvarchar(255) NOT NULL,  
    JobTitle nvarchar(50) NOT NULL,  
    RecursionLevel int NOT NULL  
)  
--Returns a result set that lists all the employees who report to the   
--specific employee directly or indirectly.*/  
AS  
BEGIN  
WITH EMP_cte(EmployeeID, OrganizationNode, FirstName, LastName, JobTitle, RecursionLevel) -- CTE name and columns  
    AS (  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, 0 -- Get the initial list of Employees for Manager n  
        FROM HumanResources.Employee e   
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        WHERE e.BusinessEntityID = @InEmpID  
        UNION ALL  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, RecursionLevel + 1 -- Join recursive member to anchor  
        FROM HumanResources.Employee e   
            INNER JOIN EMP_cte  
            ON e.OrganizationNode.GetAncestor(1) = EMP_cte.OrganizationNode  
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        )  
-- copy the required columns to the result of the function   
   INSERT @retFindReports  
   SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
   FROM EMP_cte   
   RETURN  
END;  
GO  
-- Example invocation  
SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
FROM dbo.ufn_FindReports(1);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="f10e0-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f10e0-152">See Also</span></span>  
 <span data-ttu-id="f10e0-153">[Funzioni definite dall'utente](user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="f10e0-153">[User-Defined Functions](user-defined-functions.md) </span></span>  
 [<span data-ttu-id="f10e0-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f10e0-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
