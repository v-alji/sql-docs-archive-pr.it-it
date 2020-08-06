---
title: Abilitare o disabilitare una guida di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], disabling
- enabling plan guides
- plan guides [SQL Server], enabling
- disabling plan guides
ms.assetid: b00ab550-5308-4cb8-8330-483cd1d25654
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2611697e479d318245d8306b28c826e744ae85ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721412"
---
# <a name="enable-or-disable-a-plan-guide"></a><span data-ttu-id="b6185-102">Abilitare o disabilitare una guida di piano</span><span class="sxs-lookup"><span data-stu-id="b6185-102">Enable or Disable a Plan Guide</span></span>
  <span data-ttu-id="b6185-103">È possibile disabilitare e abilitare guide di piano in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6185-103">You can disable and enable plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b6185-104">È possibile abilitare o disabilitare una sola guida di piano o tutte le guide di piano in un database.</span><span class="sxs-lookup"><span data-stu-id="b6185-104">Either a single plan guides or all plan guides in a database can be enabled or disabled.</span></span>  
  
 <span data-ttu-id="b6185-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b6185-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b6185-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b6185-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b6185-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b6185-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b6185-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b6185-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b6185-109">**Per disabilitare e abilitare le guide di piano utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="b6185-109">**To disable and enable plan guides, using:**</span></span>  
  
     [<span data-ttu-id="b6185-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b6185-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b6185-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6185-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b6185-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b6185-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b6185-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b6185-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b6185-114">Se si tenta di eliminare o modificare una funzione, una stored procedure o un trigger DML a cui viene fatto riferimento in una guida di piano abilitata o disabilitata, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="b6185-114">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="b6185-115">Verificare sempre le dipendenze prima di eliminare o modificare uno degli oggetti indicati sopra.</span><span class="sxs-lookup"><span data-stu-id="b6185-115">Always check for dependencies before dropping or modifying any of the objects listed above.</span></span>  
  
-   <span data-ttu-id="b6185-116">La disabilitazione di una guida di piano disabilitata o l'abilitazione di una guida di piano abilitata non ha alcun effetto e viene eseguita senza la restituzione di un errore.</span><span class="sxs-lookup"><span data-stu-id="b6185-116">Disabling a disabled plan guide or enabling an enabled plan guide has no effect and runs without error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b6185-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b6185-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b6185-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b6185-118">Permissions</span></span>  
 <span data-ttu-id="b6185-119">La disabilitazione o l'abilitazione di una guida di piano OBJECT richiede l'autorizzazione ALTER per l'oggetto (ad esempio funzione, stored procedure) a cui fa riferimento la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="b6185-119">Disabling or enabling an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="b6185-120">Per tutte le altre guide di piano è necessario disporre dell'autorizzazione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="b6185-120">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b6185-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b6185-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="b6185-122">Per disabilitare o abilitare una guida di piano</span><span class="sxs-lookup"><span data-stu-id="b6185-122">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="b6185-123">Fare clic sul segno più per espandere il database in cui si desidera disabilitare o abilitare una guida di piano, quindi fare clic sul segno più per espandere la cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="b6185-123">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="b6185-124">Fare clic sul segno più per espandere la cartella **Guide di piano** .</span><span class="sxs-lookup"><span data-stu-id="b6185-124">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="b6185-125">Fare clic con il pulsante destro del mouse sulla guida di piano da disabilitare o abilitare e scegliere **Abilita** o **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="b6185-125">Right-click the plan guide you want to disable or enable and select either **Disable** or **Enable**.</span></span>  
  
4.  <span data-ttu-id="b6185-126">Nella finestra di dialogo **Disabilita guida di piano** o **Abilita guida di piano** , verificare che l'azione scelta venga completata correttamente, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b6185-126">In either the **Disable Plan Guide** or **Enable Plan Guide** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="b6185-127">Per disabilitare o abilitare tutte le guide di piano in un database</span><span class="sxs-lookup"><span data-stu-id="b6185-127">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="b6185-128">Fare clic sul segno più per espandere il database in cui si desidera disabilitare o abilitare una guida di piano, quindi fare clic sul segno più per espandere la cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="b6185-128">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="b6185-129">Fare clic con il pulsante destro del mouse sulla cartella **Guide di piano** , quindi scegliere **Abilita tutto** o **Disabilita tutto**.</span><span class="sxs-lookup"><span data-stu-id="b6185-129">Right-click the **Plan Guides** folder and then select either **Enable All** or **Disable All**.</span></span>  
  
3.  <span data-ttu-id="b6185-130">Nella finestra di dialogo **Disabilita tutte le guide di piano** o **Abilita tutte le guide di piano** , verificare che l'azione scelta venga completata correttamente, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b6185-130">In either the **Disable all Plan Guides** or **Enable all Plan Guides** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b6185-131">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6185-131">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="b6185-132">Per disabilitare o abilitare una guida di piano</span><span class="sxs-lookup"><span data-stu-id="b6185-132">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="b6185-133">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6185-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6185-134">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b6185-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6185-135">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b6185-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
    --Disable the plan guide.  
    EXEC sp_control_plan_guide N'DISABLE', N'Guide3';  
    GO  
    --Enable the plan guide.  
    EXEC sp_control_plan_guide N'ENABLE', N'Guide3';  
    GO  
  
    ```  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="b6185-136">Per disabilitare o abilitare tutte le guide di piano in un database</span><span class="sxs-lookup"><span data-stu-id="b6185-136">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="b6185-137">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6185-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6185-138">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b6185-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6185-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b6185-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Disable all plan guides in the database.  
    EXEC sp_control_plan_guide N'DISABLE ALL';  
    GO  
    --Enable all plan guides in the database.  
    EXEC sp_control_plan_guide N'ENABLE ALL';  
    GO  
  
    ```  
  
 <span data-ttu-id="b6185-140">Per altre informazioni, vedere [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6185-140">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
