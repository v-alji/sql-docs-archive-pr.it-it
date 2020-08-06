---
title: MSSQLSERVER_4186 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4186 (Database Engine error)
ms.assetid: 1ae88554-f291-45bc-a186-6f41d9cd0fca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 525c1c3bd6e631044b8bc7f17b2c2a01aeb1ef8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624228"
---
# <a name="mssqlserver_4186"></a><span data-ttu-id="8e0c7-102">MSSQLSERVER_4186</span><span class="sxs-lookup"><span data-stu-id="8e0c7-102">MSSQLSERVER_4186</span></span>
    
## <a name="details"></a><span data-ttu-id="8e0c7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8e0c7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e0c7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8e0c7-104">Product Name</span></span>|<span data-ttu-id="8e0c7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e0c7-105">SQL Server</span></span>|  
|<span data-ttu-id="8e0c7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8e0c7-106">Event ID</span></span>|<span data-ttu-id="8e0c7-107">4186</span><span class="sxs-lookup"><span data-stu-id="8e0c7-107">4186</span></span>|  
|<span data-ttu-id="8e0c7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8e0c7-108">Event Source</span></span>|<span data-ttu-id="8e0c7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8e0c7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8e0c7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8e0c7-110">Component</span></span>|<span data-ttu-id="8e0c7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8e0c7-111">SQLEngine</span></span>|  
|<span data-ttu-id="8e0c7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8e0c7-112">Symbolic Name</span></span>||  
|<span data-ttu-id="8e0c7-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8e0c7-113">Message Text</span></span>|<span data-ttu-id="8e0c7-114">Colonna '%ls.%. Impossibile fare riferimento a \*ls' nella clausola OUTPUT perché la definizione di colonna contiene una sottoquery o fa riferimento a una funzione che accede a dati utente o di sistema.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-114">Column '%ls.%.\*ls' cannot be referenced in the OUTPUT clause because the column definition contains a subquery or references a function that performs user or system data access.</span></span> <span data-ttu-id="8e0c7-115">Si presuppone che le funzioni non associate a schema eseguano per impostazione predefinita l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-115">A function is assumed by default to perform data access if it is not schemabound.</span></span> <span data-ttu-id="8e0c7-116">Rimuovere la sottoquery o la funzione dalla definizione di colonna o rimuovere la colonna dalla clausola OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-116">Consider removing the subquery or function from the column definition or removing the column from the OUTPUT clause.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8e0c7-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8e0c7-117">Explanation</span></span>  
 <span data-ttu-id="8e0c7-118">Per impedire un comportamento non deterministico, la clausola OUTPUT non può fare riferimento a una colonna di una vista o di una funzione inline con valori di tabella se la colonna in questione viene definita mediante uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e0c7-118">To prevent nondeterministic behavior, the OUTPUT clause cannot reference a column from a view or inline table-valued function when that column is defined by one of the following methods:</span></span>  
  
-   <span data-ttu-id="8e0c7-119">Sottoquery.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-119">A subquery.</span></span>  
  
-   <span data-ttu-id="8e0c7-120">Funzione definita dall'utente che esegue, o si presume esegua, l'accesso ai dati dell'utente o di sistema.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-120">A user-defined function that performs user or system data access, or is assumed to perform such access.</span></span>  
  
-   <span data-ttu-id="8e0c7-121">Colonna calcolata che contiene una funzione definita dall'utente che esegue l'accesso ai dati dell'utente o di sistema nella relativa definizione.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-121">A computed column that contains a user-defined function that performs user or system data access in its definition.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="8e0c7-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="8e0c7-122">Examples</span></span>  
 <span data-ttu-id="8e0c7-123">**Visualizzare una colonna definita da una sottoquery**</span><span class="sxs-lookup"><span data-stu-id="8e0c7-123">**View Column Defined by a Subquery**</span></span>  
  
 <span data-ttu-id="8e0c7-124">Nell'esempio seguente viene creata una vista che utilizza una sottoquery dell'elenco di selezione per definire la colonna `State`.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-124">The following example creates a view that uses a subquery in the select list to define the column `State`.</span></span> <span data-ttu-id="8e0c7-125">Un'istruzione UPDATE fa quindi riferimento alla colonna `State` nella clausola OUTPUT e ha esito negativo a causa della sottoquery nell'elenco di selezione.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-125">An UPDATE statement then references the `State` column in the OUTPUT clause and fails because ob the subquery in the select list.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW dbo.V1  
AS  
    SELECT City,  
-- subquery to return the State name  
           (SELECT Name FROM Person.StateProvince AS sp   
            WHERE sp.StateProvinceID = a.StateProvinceID) AS State  
    FROM Person.Address AS a;  
GO  
--Reference the State column in the OUTPUT clause of an UPDATE statement  
UPDATE dbo.V1   
SET City = City + 'Test'   
OUTPUT deleted.City, deleted.State, inserted.City, inserted.State  
WHERE State = 'Texas';  
GO  
```  
  
 <span data-ttu-id="8e0c7-126">**Visualizzare una colonna definita da una funzione**</span><span class="sxs-lookup"><span data-stu-id="8e0c7-126">**View Column Defined by a Function**</span></span>  
  
 <span data-ttu-id="8e0c7-127">Nell'esempio seguente viene creata una vista che usa la funzione scalare di accesso ai dati `dbo.ufnGetStock`dell'elenco di selezione per definire la colonna `CurrentInventory`.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-127">The following example creates a view that uses the data accessing, scalar function `dbo.ufnGetStock` in the select list to define the column `CurrentInventory`.</span></span> <span data-ttu-id="8e0c7-128">Un'istruzione UPDATE fa quindi riferimento alla colonna `CurrentInventory` nella clausola OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-128">An UPDATE statement then references the `CurrentInventory` column in the OUTPUT clause .</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW Production.ReorderLevels  
AS  
    SELECT ProductID, ProductModelID, ReorderPoint,  
           dbo.ufnGetStock(ProductID) AS CurrentInventory  
    FROM Production.Product;  
GO  
  
UPDATE Production.ReorderLevels  
SET ReorderPoint += CurrentInventory  
OUTPUT deleted.ReorderPoint, deleted.CurrentInventory,  
       inserted.ReorderPoint, inserted.CurrentInventory  
WHERE ProductModelID BETWEEN 75 and 80;  
```  
  
## <a name="user-action"></a><span data-ttu-id="8e0c7-129">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8e0c7-129">User Action</span></span>  
 <span data-ttu-id="8e0c7-130">È possibile correggere l'errore 4186 in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e0c7-130">Error 4186 can be corrected in one of the following ways:</span></span>  
  
-   <span data-ttu-id="8e0c7-131">Utilizzare i join anziché le sottoquery per definire la colonna nella vista o nella funzione.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-131">Use joins instead of subqueries to define the column in the view or function.</span></span> <span data-ttu-id="8e0c7-132">È ad esempio possibile riscrivere la vista `dbo.V1` come segue.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-132">For example, you can rewrite the view `dbo.V1` as follows.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE VIEW dbo.V1  
    AS  
        SELECT City, sp.Name AS State  
        FROM Person.Address AS a   
        JOIN Person.StateProvince AS sp   
        ON sp.StateProvinceID = a.StateProvinceID;  
    ```  
  
-   <span data-ttu-id="8e0c7-133">Esaminare la definizione della funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-133">Examine the definition of the user-defined function.</span></span> <span data-ttu-id="8e0c7-134">Se la funzione non esegue l'accesso ai dati dell'utente o del sistema, modificarla in modo da includere la clausola WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-134">If the function does not perform user or system data access, alter the function to include the WITH SCHEMABINDING clause.</span></span>  
  
-   <span data-ttu-id="8e0c7-135">Rimuovere la colonna dalla clausola OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="8e0c7-135">Remove the column from the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e0c7-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e0c7-136">See Also</span></span>  
 [<span data-ttu-id="8e0c7-137">Clausola OUTPUT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8e0c7-137">OUTPUT Clause &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/output-clause-transact-sql)  
  
  
