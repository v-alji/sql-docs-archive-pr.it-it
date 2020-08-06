---
title: Eliminare funzioni definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: db1d668a-23b7-4757-a9c5-1bd848ba7f6d
author: rothja
ms.author: jroth
ms.openlocfilehash: e5f6b2b306c4fe8db08b088d9607cfb19ab0f25e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637112"
---
# <a name="delete-user-defined-functions"></a><span data-ttu-id="50efa-102">Eliminare funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="50efa-102">Delete User-defined Functions</span></span>
  <span data-ttu-id="50efa-103">È possibile eliminare funzioni definite dall'utente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50efa-103">You can delete (drop) user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="50efa-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="50efa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="50efa-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="50efa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="50efa-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="50efa-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="50efa-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="50efa-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="50efa-108">**Eliminare una funzione definita dall'utente tramite:**</span><span class="sxs-lookup"><span data-stu-id="50efa-108">**To delete a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="50efa-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50efa-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="50efa-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50efa-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="50efa-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="50efa-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="50efa-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="50efa-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="50efa-113">Non è possibile eliminare la funzione se nel database sono presenti funzioni o viste Transact-SQL che fanno riferimento a questa funzione e che sono state create tramite SCHEMABINDING oppure se sono presenti colonne calcolate, vincoli CHECK o vincoli DEFAULT che fanno riferimento alla funzione.</span><span class="sxs-lookup"><span data-stu-id="50efa-113">You will not be able to delete the function if there are Transact-SQL functions or views in the database that reference this function and were created by using SCHEMABINDING, or if there are computed columns, CHECK constraints, or DEFAULT constraints that reference the function.</span></span>  
  
-   <span data-ttu-id="50efa-114">Non è possibile eliminare la funzione se sono presenti colonne calcolate che fanno riferimento alla funzione e che sono state indicizzate.</span><span class="sxs-lookup"><span data-stu-id="50efa-114">You will not be able to delete the function if there are computed columns that reference this function and have been indexed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="50efa-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="50efa-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="50efa-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="50efa-116">Permissions</span></span>  
 <span data-ttu-id="50efa-117">È necessaria l'autorizzazione ALTER per lo schema a cui appartiene la funzione o l'autorizzazione CONTROL per la funzione.</span><span class="sxs-lookup"><span data-stu-id="50efa-117">Requires ALTER permission on the schema to which the function belongs, or CONTROL permission on the function.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="50efa-118">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50efa-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="50efa-119">Per eliminare una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="50efa-119">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="50efa-120">Fare clic sul segno più accanto al database che contiene la funzione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="50efa-120">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="50efa-121">Fare clic sul segno più accanto alla cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="50efa-121">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="50efa-122">Fare clic sul segno più accanto alla cartella che contiene la funzione che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="50efa-122">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="50efa-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="50efa-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="50efa-124">Funzione a valori scalari</span><span class="sxs-lookup"><span data-stu-id="50efa-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="50efa-125">Funzione di aggregazione</span><span class="sxs-lookup"><span data-stu-id="50efa-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="50efa-126">Fare clic con il pulsante destro del mouse sulla funzione che si desidera eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="50efa-126">Right-click the function you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="50efa-127">Nella finestra di dialogo **Elimina oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="50efa-127">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="50efa-128">Fare clic su **Mostra dipendenze** nella finestra di dialogo **Elimina oggetto** per aprire la finestra di dialogo**dipendenze** _function_name_.</span><span class="sxs-lookup"><span data-stu-id="50efa-128">Click **Show Dependencies** in the **Delete Object** dialog box to open the _function_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="50efa-129">Verranno visualizzati tutti gli oggetti che dipendono dalla funzione e tutti gli oggetti da cui dipende la funzione.</span><span class="sxs-lookup"><span data-stu-id="50efa-129">This will show all of the objects that depend on the function and all of the objects on which the function depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="50efa-130">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50efa-130">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="50efa-131">Per eliminare una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="50efa-131">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="50efa-132">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50efa-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="50efa-133">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="50efa-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="50efa-134">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="50efa-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates function called "Sales.ufn_SalesByStore"  
    USE AdventureWorks2012;  
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
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- determines if function exists in database  
    IF OBJECT_ID (N'Sales.fn_SalesByStore', N'IF') IS NOT NULL  
    -- deletes function  
        DROP FUNCTION Sales.fn_SalesByStore;  
    GO  
    ```  
  
 <span data-ttu-id="50efa-135">Per altre informazioni, vedere [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50efa-135">For more information, see [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
  
