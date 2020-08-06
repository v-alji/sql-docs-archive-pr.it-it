---
title: 'Esercitazione: Catene di proprietà e cambio di contesto'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- context switching [SQL Server], tutorials
- ownership chains [SQL Server]
ms.assetid: db5d4cc3-5fc5-4cf5-afc1-8d4edc1d512b
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e9072a68dd3179e5900fda06d4fea58b484a37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626614"
---
# <a name="tutorial-ownership-chains-and-context-switching"></a><span data-ttu-id="59b76-102">Tutorial: Ownership Chains and Context Switching</span><span class="sxs-lookup"><span data-stu-id="59b76-102">Tutorial: Ownership Chains and Context Switching</span></span>
  <span data-ttu-id="59b76-103">In questa esercitazione viene utilizzato uno scenario per illustrare i concetti sulla sicurezza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relativi a catene di proprietà e cambio di contesto utente.</span><span class="sxs-lookup"><span data-stu-id="59b76-103">This tutorial uses a scenario to illustrate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security concepts involving ownership chains and user context switching.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b76-104">Per eseguire il codice dell'esercitazione deve essere configurata la sicurezza a modalità mista e deve essere installato il database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59b76-104">To run the code in this tutorial you must have both Mixed Mode security configured and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database installed.</span></span> <span data-ttu-id="59b76-105">Per altre informazioni sulla sicurezza in modalità mista, vedere [Scegliere una modalità di autenticazione](security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="59b76-105">For more information about Mixed Mode security, see [Choose an Authentication Mode](security/choose-an-authentication-mode.md).</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="59b76-106">Scenario</span><span class="sxs-lookup"><span data-stu-id="59b76-106">Scenario</span></span>  
 <span data-ttu-id="59b76-107">In questo scenario due utenti necessitano degli account per accedere ai dati relativi agli ordini di acquisto archiviati nel database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59b76-107">In this scenario, two users need accounts to access purchase order data stored in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="59b76-108">È necessario soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="59b76-108">The requirements are as follows:</span></span>  
  
-   <span data-ttu-id="59b76-109">Il primo account (TestManagerUser) deve essere in grado di visualizzare tutti i dettagli di ogni ordine di acquisto.</span><span class="sxs-lookup"><span data-stu-id="59b76-109">The first account (TestManagerUser) must be able to see all details in every purchase order.</span></span>  
  
-   <span data-ttu-id="59b76-110">Il secondo account (TestEmployeeUser) deve essere in grado di visualizzare il numero dell'ordine di acquisto, la data dell'ordine, la data di spedizione, i numeri di serie dei prodotti e gli articoli ordinati e ricevuti per ordine di acquisto, in base al numero di ordine di acquisto, per gli articoli per i quali sono state eseguite spedizioni parziali.</span><span class="sxs-lookup"><span data-stu-id="59b76-110">The second account (TestEmployeeUser) must be able to see the purchase order number, order date, shipping date, product ID numbers, and the ordered and received items per purchase order, by purchase order number, for items where partial shipments have been received.</span></span>  
  
-   <span data-ttu-id="59b76-111">Tutti gli altri account devono mantenere le autorizzazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="59b76-111">All other accounts must retain their current permissions.</span></span>  
  
 <span data-ttu-id="59b76-112">Per soddisfare i requisiti di questo scenario, l'esempio è suddiviso in quattro parti in cui vengono illustrati i concetti delle catene di proprietà e dello scambio di contesto:</span><span class="sxs-lookup"><span data-stu-id="59b76-112">To fulfill the requirements of this scenario, the example is broken into four parts that demonstrate the concepts of ownership chains and context switching:</span></span>  
  
1.  <span data-ttu-id="59b76-113">Configurazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="59b76-113">Configuring the environment.</span></span>  
  
2.  <span data-ttu-id="59b76-114">Creazione di una stored procedure per l'accesso ai dati in base all'ordine di acquisto.</span><span class="sxs-lookup"><span data-stu-id="59b76-114">Creating a stored procedure to access data by purchase order.</span></span>  
  
3.  <span data-ttu-id="59b76-115">Accesso ai dati tramite la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="59b76-115">Accessing the data through the stored procedure.</span></span>  
  
4.  <span data-ttu-id="59b76-116">Reimpostazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="59b76-116">Resetting the environment.</span></span>  
  
 <span data-ttu-id="59b76-117">Ogni blocco di codice dell'esempio è illustrato sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="59b76-117">Each code block in this example is explained in line.</span></span> <span data-ttu-id="59b76-118">Per copiare l'esempio completo, vedere [Esempio completo](#CompleteExample) alla fine dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="59b76-118">To copy the complete example, see [Complete Example](#CompleteExample) at the end of this tutorial.</span></span>  
  
## <a name="1-configure-the-environment"></a><span data-ttu-id="59b76-119">1. Configurazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="59b76-119">1. Configure the Environment</span></span>  
 <span data-ttu-id="59b76-120">Utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e il codice seguente per aprire il `AdventureWorks2012` database e utilizzare l' `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] istruzione per verificare che l'utente dbo venga visualizzato come contesto.</span><span class="sxs-lookup"><span data-stu-id="59b76-120">Use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and the following code to open the `AdventureWorks2012` database, and use the `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] statement to check that the dbo user is displayed as the context.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
```  
  
 <span data-ttu-id="59b76-121">Per altre informazioni sull'istruzione CURRENT_USER, vedere [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59b76-121">For more information about the CURRENT_USER statement, see [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span></span>  
  
 <span data-ttu-id="59b76-122">Utilizzare questo codice come utente dbo per creare due utenti nel server e nel database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59b76-122">Use this code as the dbo user to create two users on the server and in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
GO  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
```  
  
 <span data-ttu-id="59b76-123">Per altre informazioni sull'istruzione CREATE USER, vedere [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59b76-123">For more information about the CREATE USER statement, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="59b76-124">Per altre informazioni sull'istruzione CREATE LOGIN, vedere [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59b76-124">For more information about the CREATE LOGIN statement, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
 <span data-ttu-id="59b76-125">Utilizzare il codice seguente per modificare la proprietà dello schema `Purchasing` e impostarla sull'account `TestManagerUser` .</span><span class="sxs-lookup"><span data-stu-id="59b76-125">Use the following code to change the ownership of the `Purchasing` schema to the `TestManagerUser` account.</span></span> <span data-ttu-id="59b76-126">In questo modo si consente all'account di utilizzare l'accesso completo alle istruzioni DML (Data Manipulation Language), ad esempio autorizzazioni `SELECT` e `INSERT` , sull'oggetto contenuto.</span><span class="sxs-lookup"><span data-stu-id="59b76-126">This allows that account to use all Data Manipulation Language (DML) statement access (such as `SELECT` and `INSERT` permissions) on the objects it contains.</span></span> <span data-ttu-id="59b76-127">`TestManagerUser` viene inoltre concessa la possibilità di creare stored procedure.</span><span class="sxs-lookup"><span data-stu-id="59b76-127">`TestManagerUser` is also granted the ability to create stored procedures.</span></span>  
  
```  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
```  
  
 <span data-ttu-id="59b76-128">Per altre informazioni sull'istruzione GRANT, vedere [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59b76-128">For more information about the GRANT statement, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="59b76-129">Per altre informazioni sulle stored procedure, vedere [Stored procedure &#40;Motore di database&#41;](stored-procedures/stored-procedures-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="59b76-129">For more information about stored procedures, see [Stored Procedures &#40;Database Engine&#41;](stored-procedures/stored-procedures-database-engine.md).</span></span> <span data-ttu-id="59b76-130">Per un poster di tutte le [!INCLUDE[ssDE](../includes/ssde-md.md)] autorizzazioni, vedere [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf) .</span><span class="sxs-lookup"><span data-stu-id="59b76-130">For a poster of all [!INCLUDE[ssDE](../includes/ssde-md.md)] permissions, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>  
  
## <a name="2-create-a-stored-procedure-to-access-data"></a><span data-ttu-id="59b76-131">2. Creazione di una stored procedure per l'accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="59b76-131">2. Create a Stored Procedure to Access Data</span></span>  
 <span data-ttu-id="59b76-132">Per cambiare contesto all'interno di un database, utilizzare l'istruzione EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="59b76-132">To switch context within a database, use the EXECUTE AS statement.</span></span> <span data-ttu-id="59b76-133">EXECUTE AS richiede autorizzazioni IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="59b76-133">EXECUTE AS requires IMPERSONATE permissions.</span></span>  
  
 <span data-ttu-id="59b76-134">Utilizzare l'istruzione `EXECUTE AS` del codice seguente per cambiare il contesto impostandolo su `TestManagerUser` e creare una stored procedure in grado di visualizzare soltanto i dati necessari per `TestEmployeeUser`.</span><span class="sxs-lookup"><span data-stu-id="59b76-134">Use the `EXECUTE AS` statement in the following code to change the context to `TestManagerUser` and create a stored procedure showing only the data required by `TestEmployeeUser`.</span></span> <span data-ttu-id="59b76-135">Per soddisfare i requisiti, la stored procedure accetta una variabile per il numero dell'ordine di acquisto e non visualizza informazioni finanziarie. La clausola WHERE limita inoltre i risultati alle spedizioni parziali.</span><span class="sxs-lookup"><span data-stu-id="59b76-135">To satisfy the requirements, the stored procedure accepts one variable for the purchase order number and does not display financial information, and the WHERE clause limits the results to partial shipments.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestManagerUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader a  
      INNER JOIN Purchasing.PurchaseOrderDetail b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END  
GO  
```  
  
 <span data-ttu-id="59b76-136">`TestEmployeeUser` non dispone attualmente dell'accesso a qualsiasi oggetto di database.</span><span class="sxs-lookup"><span data-stu-id="59b76-136">Currently `TestEmployeeUser` does not have access to any database objects.</span></span> <span data-ttu-id="59b76-137">Il codice seguente, ancora nel contesto `TestManagerUser` , concede all'account utente la possibilità di eseguire query sulle informazioni delle tabelle di base tramite la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="59b76-137">The following code (still in the `TestManagerUser` context) grants the user account the ability to query base-table information through the stored procedure.</span></span>  
  
```  
GRANT EXECUTE  
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO  
```  
  
 <span data-ttu-id="59b76-138">La stored procedure appartiene allo schema `Purchasing` , nonostante non venga specificato esplicitamente uno schema, poiché `TestManagerUser` è assegnato per impostazione predefinita allo schema `Purchasing` .</span><span class="sxs-lookup"><span data-stu-id="59b76-138">The stored procedure is part of the `Purchasing` schema, even though no schema was explicitly specified, because `TestManagerUser` is assigned by default to the `Purchasing` schema.</span></span> <span data-ttu-id="59b76-139">È possibile utilizzare le informazioni del catalogo di sistema per individuare gli oggetti, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="59b76-139">You can use system catalog information to locate objects, as shown in the following code.</span></span>  
  
```  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas a  
   INNER JOIN sys.objects b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
```  
  
 <span data-ttu-id="59b76-140">Al termine di questa sezione dell'esempio, nel codice il contesto viene cambiato e nuovamente impostato su dbo mediante l'istruzione `REVERT`.</span><span class="sxs-lookup"><span data-stu-id="59b76-140">With this section of the example completed, the code switches context back to dbo using the `REVERT` statement.</span></span>  
  
```  
REVERT;  
GO  
```  
  
 <span data-ttu-id="59b76-141">Per altre informazioni sull'istruzione REVERT, vedere [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59b76-141">For more information about the REVERT statement, see [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span></span>  
  
## <a name="3-access-data-through-the-stored-procedure"></a><span data-ttu-id="59b76-142">3. Accesso ai dati tramite la stored procedure</span><span class="sxs-lookup"><span data-stu-id="59b76-142">3. Access Data Through the Stored Procedure</span></span>  
 <span data-ttu-id="59b76-143">`TestEmployeeUser` non dispone di autorizzazioni per gli oggetti di database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] ad eccezione dell'accesso e dei diritti assegnati al ruolo di database public.</span><span class="sxs-lookup"><span data-stu-id="59b76-143">`TestEmployeeUser` has no permissions on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database objects other than a login and the rights assigned to the public database role.</span></span> <span data-ttu-id="59b76-144">Quando `TestEmployeeUser` tenta di accedere alle tabelle di base, il codice seguente restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="59b76-144">The following code returns an error when `TestEmployeeUser` attempts to access base tables.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestEmployeeUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* This won't work */  
SELECT *  
FROM Purchasing.PurchaseOrderHeader;  
GO  
SELECT *  
FROM Purchasing.PurchaseOrderDetail;  
GO  
```  
  
 <span data-ttu-id="59b76-145">Poiché gli oggetti a cui fa riferimento la stored procedure creata nell'ultima sezione sono di proprietà di `TestManagerUser` in virtù della proprietà dello schema `Purchasing` , `TestEmployeeUser` può accedere alle tabelle di base tramite la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="59b76-145">Because the objects referenced by the stored procedure created in the last section are owned by `TestManagerUser` by virtue of the `Purchasing` schema ownership, `TestEmployeeUser` can access the base tables through the stored procedure.</span></span> <span data-ttu-id="59b76-146">Nel codice seguente, in cui viene ancora utilizzato `TestEmployeeUser` come contesto, viene passato l'ordine di acquisto 952 come parametro.</span><span class="sxs-lookup"><span data-stu-id="59b76-146">The following code, still using the `TestEmployeeUser` context, passes purchase order 952 as a parameter.</span></span>  
  
```  
EXEC Purchasing.usp_ShowWaitingItems 952  
GO  
```  
  
## <a name="4-reset-the-environment"></a><span data-ttu-id="59b76-147">4. Reimpostazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="59b76-147">4. Reset the Environment</span></span>  
 <span data-ttu-id="59b76-148">Nel codice seguente viene utilizzato il comando `REVERT` per ripristinare `dbo`come contesto dell'account corrente e quindi viene reimpostato l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="59b76-148">The following code uses the `REVERT` command to return the context of the current account to `dbo`, and then resets the environment.</span></span>  
  
```  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
##  <a name="complete-example"></a><a name="CompleteExample"></a><span data-ttu-id="59b76-149">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="59b76-149">Complete Example</span></span>  
 <span data-ttu-id="59b76-150">In questa sezione è riportato il codice completo dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="59b76-150">This section displays the complete example code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b76-151">Nel codice non sono inclusi i due errori previsti che dimostrano l'impossibilità per `TestEmployeeUser` di eseguire una selezione nelle tabelle di base.</span><span class="sxs-lookup"><span data-stu-id="59b76-151">This code does not include the two expected errors that demonstrate the inability of `TestEmployeeUser` to select from base tables.</span></span>  
  
```  
/*   
Script:       UserContextTutorial.sql  
Author:       Microsoft  
Last Updated: Books Online  
Conditions:   Execute as DBO or sysadmin in the AdventureWorks database  
Section 1:    Configure the Environment   
*/  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* Create server and database users */  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
  
GO  
  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
  
/*   
Section 2: Switch Context and Create Objects  
*/  
EXECUTE AS LOGIN = 'TestManagerUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader AS a  
      INNER JOIN Purchasing.PurchaseOrderDetail AS b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END;  
GO  
  
/* Give the employee the ability to run the procedure */  
GRANT EXECUTE   
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO   
  
/* Notice that the stored procedure is located in the Purchasing   
schema. This also demonstrates system catalogs */  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas AS a  
   INNER JOIN sys.objects AS b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
  
/* Go back to being the dbo user */  
REVERT;  
GO  
  
/*  
Section 3: Switch Context and Observe Security   
*/  
EXECUTE AS LOGIN = 'TestEmployeeUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
EXEC Purchasing.usp_ShowWaitingItems 952;  
GO  
  
/*   
Section 4: Clean Up Example  
*/  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="59b76-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59b76-152">See Also</span></span>  
 [<span data-ttu-id="59b76-153">Centro sicurezza per il motore di Database di SQL Server e il Database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="59b76-153">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
