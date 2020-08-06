---
title: Modificare funzioni definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 891c37b3-cb72-411f-9937-ee87e6d95f34
author: rothja
ms.author: jroth
ms.openlocfilehash: 1cf25fef91834e237f5cbaac26350220840830bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637109"
---
# <a name="modify-user-defined-functions"></a><span data-ttu-id="69999-102">Modificare funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="69999-102">Modify User-defined Functions</span></span>
  <span data-ttu-id="69999-103">È possibile modificare le funzioni definite dall'utente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69999-103">You can modify user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="69999-104">La modifica delle funzioni definite dall'utente come descritto di seguito non comporta la modifica delle autorizzazioni delle funzioni, né influisce su funzioni dipendenti, stored procedure o trigger.</span><span class="sxs-lookup"><span data-stu-id="69999-104">Modifying user-defined functions as described below will not change the functions' permissions, nor will it affect any dependent functions, stored procedures, or triggers.</span></span>  
  
 <span data-ttu-id="69999-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="69999-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="69999-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="69999-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="69999-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="69999-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="69999-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="69999-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="69999-109">**Per modificare una funzione definita dall'utente tramite:**</span><span class="sxs-lookup"><span data-stu-id="69999-109">**To modify a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="69999-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69999-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="69999-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69999-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="69999-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="69999-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="69999-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="69999-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="69999-114">Non è possibile utilizzare ALTER FUNCTION per eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="69999-114">ALTER FUNCTION cannot be used to perform any of the following actions:</span></span>  
  
-   <span data-ttu-id="69999-115">Modificare una funzione a valori scalari in una funzione con valori di tabella o viceversa.</span><span class="sxs-lookup"><span data-stu-id="69999-115">Change a scalar-valued function to a table-valued function, or vice versa.</span></span>  
  
-   <span data-ttu-id="69999-116">Modificare una funzione inline in una funzione a più istruzioni o viceversa.</span><span class="sxs-lookup"><span data-stu-id="69999-116">Change an inline function to a multistatement function, or vice versa.</span></span>  
  
-   <span data-ttu-id="69999-117">Modificare una funzione Transact-SQL in una funzione CLR o viceversa.</span><span class="sxs-lookup"><span data-stu-id="69999-117">Change a Transact-SQL function to a CLR function, or vice-versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="69999-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="69999-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="69999-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="69999-119">Permissions</span></span>  
 <span data-ttu-id="69999-120">È necessario disporre dell'autorizzazione ALTER per la funzione o lo schema.</span><span class="sxs-lookup"><span data-stu-id="69999-120">Requires ALTER permission on the function or on the schema.</span></span> <span data-ttu-id="69999-121">Se per la funzione viene specificato un tipo definito dall'utente, è necessario disporre dell'autorizzazione EXECUTE per tale tipo.</span><span class="sxs-lookup"><span data-stu-id="69999-121">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="69999-122">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69999-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="69999-123">Per modificare una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="69999-123">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="69999-124">Fare clic sul segno più accanto al database che contiene la funzione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="69999-124">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="69999-125">Fare clic sul segno più accanto alla cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="69999-125">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="69999-126">Fare clic sul segno più accanto alla cartella che contiene la funzione che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="69999-126">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="69999-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="69999-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="69999-128">Funzione a valori scalari</span><span class="sxs-lookup"><span data-stu-id="69999-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="69999-129">Funzione di aggregazione</span><span class="sxs-lookup"><span data-stu-id="69999-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="69999-130">Fare clic con il pulsante destro del mouse sulla funzione da modificare, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="69999-130">Right-click the function you want to modify and select **Modify**.</span></span>  
  
5.  <span data-ttu-id="69999-131">Nella Finestra Query apportare le modifiche necessarie all'istruzione ALTER FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="69999-131">In the Query Window, make the necessary changes to the ALTER FUNCTION statement.</span></span>  
  
6.  <span data-ttu-id="69999-132">Dal menu **File** scegliere **Salva**_nome_funzione_.</span><span class="sxs-lookup"><span data-stu-id="69999-132">On the **File** menu, click **Save**_function_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="69999-133">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69999-133">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="69999-134">Per modificare una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="69999-134">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="69999-135">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69999-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="69999-136">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="69999-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="69999-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="69999-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Scalar-Valued Function  
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetAccountingEndDate]()  
    RETURNS [datetime]   
    AS   
    BEGIN  
        RETURN DATEADD(millisecond, -2, CONVERT(datetime, '20040701', 112));  
    END;  
    ```  
  
    ```  
    -- Table-Valued Function   
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetContactInformation](@PersonID int)  
    RETURNS @retContactInformation TABLE   
    (  
        -- Columns returned by the function  
        [PersonID] int NOT NULL,   
        [FirstName] [nvarchar](50) NULL,   
        [LastName] [nvarchar](50) NULL,   
        [JobTitle] [nvarchar](50) NULL,  
        [BusinessEntityType] [nvarchar](50) NULL  
    )  
    AS   
    -- Returns the first name, last name, job title and business entity type for the specified contact.  
    -- Since a contact can serve multiple roles, more than one row may be returned.  
    BEGIN  
    IF @PersonID IS NOT NULL   
    BEGIN  
         IF EXISTS(SELECT * FROM [HumanResources].[Employee] e   
         WHERE e.[BusinessEntityID] = @PersonID)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, e.[JobTitle], 'Employee'  
              FROM [HumanResources].[Employee] AS e  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = e.[BusinessEntityID]  
              WHERE e.[BusinessEntityID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Purchasing].[Vendor] AS v  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Vendor Contact'   
              FROM [Purchasing].[Vendor] AS v  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Sales].[Store] AS s  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Store Contact'   
              FROM [Sales].[Store] AS s  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Person].[Person] AS p  
         INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
         WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, NULL, 'Consumer'   
              FROM [Person].[Person] AS p  
              INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
              WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL;   
         END  
    RETURN;  
    END;  
    ```  
  
 <span data-ttu-id="69999-138">Per altre informazioni, vedere [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69999-138">For more information, see [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span></span>  
  
  
