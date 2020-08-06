---
title: Eliminare una guida di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], deleting
ms.assetid: aa4d3188-6927-43de-a3e3-90fc16eeaca7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 303ad6f59cbe24265aec66f3cb780a5b4ad4f157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714223"
---
# <a name="delete-a-plan-guide"></a><span data-ttu-id="8893b-102">Eliminare una guida di piano</span><span class="sxs-lookup"><span data-stu-id="8893b-102">Delete a Plan Guide</span></span>
  <span data-ttu-id="8893b-103">È possibile eliminare una guida di piano in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8893b-103">You can delete (drop) a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8893b-104">Tramite [!INCLUDE[tsql](../../includes/tsql-md.md)]è inoltre possibile eliminare tutte le guide di piano in un database.</span><span class="sxs-lookup"><span data-stu-id="8893b-104">Using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can also delete all of the plan guides in a database.</span></span>  
  
 <span data-ttu-id="8893b-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8893b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8893b-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8893b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8893b-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8893b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8893b-108">**Per eliminare una guida di piano utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="8893b-108">**To delete a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="8893b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8893b-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8893b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8893b-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8893b-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8893b-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8893b-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8893b-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8893b-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8893b-113">Permissions</span></span>  
 <span data-ttu-id="8893b-114">L'eliminazione di una guida di piano OBJECT richiede l'autorizzazione ALTER per l'oggetto (ad esempio funzione, stored procedure) a cui fa riferimento la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="8893b-114">Deleting an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="8893b-115">Per tutte le altre guide di piano è necessario disporre dell'autorizzazione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="8893b-115">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8893b-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8893b-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-plan-guide"></a><span data-ttu-id="8893b-117">Per eliminare una guida di piano</span><span class="sxs-lookup"><span data-stu-id="8893b-117">To delete a plan guide</span></span>  
  
1.  <span data-ttu-id="8893b-118">Fare clic sul segno più per espandere il database in cui si desidera eliminare una guida di piano, quindi fare clic sul segno più per espandere la cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="8893b-118">Click the plus sign to expand the database in which you want to delete a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="8893b-119">Fare clic sul segno più per espandere la cartella **Guide di piano** .</span><span class="sxs-lookup"><span data-stu-id="8893b-119">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="8893b-120">Fare clic con il pulsante destro del mouse sulla guida di piano da eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8893b-120">Right-click the plan guide you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="8893b-121">Nella finestra di dialogo **Elimina oggetto** verificare che venga selezionata la guida di piano corretta, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8893b-121">In the **Delete Object** dialog box, ensure that the correct plan guide is selected and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8893b-122">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8893b-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-single-plan-guide"></a><span data-ttu-id="8893b-123">Per eliminare una singola guida di piano:</span><span class="sxs-lookup"><span data-stu-id="8893b-123">To delete a single plan guide</span></span>  
  
1.  <span data-ttu-id="8893b-124">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8893b-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8893b-125">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8893b-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8893b-126">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8893b-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Create a procedure on which to define the plan guide.  
    IF OBJECT_ID(N'Sales.GetSalesOrderByCountry', N'P') IS NOT NULL  
        DROP PROCEDURE Sales.GetSalesOrderByCountry;  
    GO  
    CREATE PROCEDURE Sales.GetSalesOrderByCountry   
        (@Country nvarchar(60))  
    AS  
    BEGIN  
        SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country;  
    END  
    GO  
    --Create the plan guide.  
    EXEC sp_create_plan_guide N'Guide3',  
        N'SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country',  
        N'OBJECT',  
        N'Sales.GetSalesOrderByCountry',  
        NULL,  
        N'OPTION (OPTIMIZE FOR (@Country = N''US''))';  
    GO  
    --Drop the plan guide.  
    EXEC sp_control_plan_guide N'DROP', N'Guide3';  
    GO  
    ```  
  
#### <a name="to-delete-all-plan-guides-in-a-database"></a><span data-ttu-id="8893b-127">Per eliminare tutte le guide di piano in un database</span><span class="sxs-lookup"><span data-stu-id="8893b-127">To delete all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="8893b-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8893b-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8893b-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8893b-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8893b-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8893b-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_control_plan_guide N'DROP ALL';  
    GO  
    ```  
  
 <span data-ttu-id="8893b-131">Per altre informazioni, vedere [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8893b-131">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
