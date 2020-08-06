---
title: Aggiornare le statistiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- updating statistics
- statistics [SQL Server], updating
ms.assetid: 4b97c0b4-03ff-4cfb-9c3f-3b33290b7a2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 28491dda23c2ba9402e91dc051249f5bdcdf28d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636617"
---
# <a name="update-statistics"></a><span data-ttu-id="50789-102">Aggiorna statistiche</span><span class="sxs-lookup"><span data-stu-id="50789-102">Update Statistics</span></span>
  <span data-ttu-id="50789-103">È possibile aggiornare le statistiche di ottimizzazione delle query per una tabella o una vista indicizzata in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50789-103">You can update query optimization statistics on a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="50789-104">Per impostazione predefinita, tramite Query Optimizer vengono già aggiornate le statistiche nel modo necessario per migliorare il piano di query. In alcuni casi, è possibile migliorare le prestazioni di esecuzione delle query utilizzando UPDATE STATISTICS o la stored procedure `sp_updatestats` per aggiornare le statistiche con una maggiore frequenza rispetto agli aggiornamenti predefiniti.</span><span class="sxs-lookup"><span data-stu-id="50789-104">By default, the query optimizer already updates statistics as necessary to improve the query plan; in some cases you can improve query performance by using UPDATE STATISTICS or the stored procedure `sp_updatestats` to update statistics more frequently than the default updates.</span></span>  
  
 <span data-ttu-id="50789-105">Sebbene consenta di garantire che le query vengano compilate con statistiche aggiornate,</span><span class="sxs-lookup"><span data-stu-id="50789-105">Updating statistics ensures that queries compile with up-to-date statistics.</span></span> <span data-ttu-id="50789-106">l'aggiornamento delle statistiche causa la ricompilazione delle query.</span><span class="sxs-lookup"><span data-stu-id="50789-106">However, updating statistics causes queries to recompile.</span></span> <span data-ttu-id="50789-107">Si consiglia di non aggiornare le statistiche troppo frequentemente perché è necessario mantenere un equilibrio a livello di prestazioni tra la necessità di migliorare i piani di query e il tempo necessario per la ricompilazione delle query.</span><span class="sxs-lookup"><span data-stu-id="50789-107">We recommend not updating statistics too frequently because there is a performance tradeoff between improving query plans and the time it takes to recompile queries.</span></span> <span data-ttu-id="50789-108">Tale equilibrio dipende dall'applicazione in uso.</span><span class="sxs-lookup"><span data-stu-id="50789-108">The specific tradeoffs depend on your application.</span></span> <span data-ttu-id="50789-109">Per le operazioni UPDATE STATISTICS è possibile usare tempdb per ordinare l'esempio di righe per la compilazione di statistiche.</span><span class="sxs-lookup"><span data-stu-id="50789-109">UPDATE STATISTICS can use tempdb to sort the sample of rows for building statistics.</span></span>  
  
 <span data-ttu-id="50789-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="50789-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="50789-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="50789-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="50789-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="50789-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="50789-113">**Aggiornare un oggetto statistiche tramite:**</span><span class="sxs-lookup"><span data-stu-id="50789-113">**To update a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="50789-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50789-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="50789-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50789-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="50789-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="50789-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="50789-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="50789-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="50789-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="50789-118">Permissions</span></span>  
 <span data-ttu-id="50789-119">Se si utilizza UPDATE STATISTICS o si apportano modifiche tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], è necessaria l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="50789-119">If using UPDATE STATISTICS or making changes through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], requires ALTER permission on the table or view.</span></span> <span data-ttu-id="50789-120">Se si usa `sp_updatestats`, è necessario essere un membro del ruolo predefinito del server **sysadmin** o il proprietario del database (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="50789-120">If using `sp_updatestats`, requires membership in the **sysadmin** fixed server role, or ownership of the database (**dbo**).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="50789-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50789-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-update-a-statistics-object"></a><span data-ttu-id="50789-122">Per aggiornare un oggetto statistiche</span><span class="sxs-lookup"><span data-stu-id="50789-122">To update a statistics object</span></span>  
  
1.  <span data-ttu-id="50789-123">In **Esplora oggetti**fare clic sul segno più per espandere il database in cui si desidera aggiornare la statistica.</span><span class="sxs-lookup"><span data-stu-id="50789-123">In **Object Explorer**, click the plus sign to expand the database in which you want to update the statistic.</span></span>  
  
2.  <span data-ttu-id="50789-124">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="50789-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="50789-125">Fare clic sul segno più per espandere la tabella in cui si desidera aggiornare la statistica.</span><span class="sxs-lookup"><span data-stu-id="50789-125">Click the plus sign to expand the table in which you want to update the statistic.</span></span>  
  
4.  <span data-ttu-id="50789-126">Fare clic sul segno più per espandere la cartella **Statistiche** .</span><span class="sxs-lookup"><span data-stu-id="50789-126">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="50789-127">Fare clic con il pulsante destro del mouse sull'oggetto che si vuole aggiornare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="50789-127">Right-click the statistics object you wish to update and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="50789-128">Nella finestra di dialogo **proprietà statistiche-**_statistics_name_ Selezionare la casella di controllo **Aggiorna statistiche per le colonne seguenti** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="50789-128">In the **Statistics Properties -**_statistics_name_ dialog box, select the **Update statistics for these columns** check box and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="50789-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50789-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-a-specific-statistics-object"></a><span data-ttu-id="50789-130">Per aggiornare un oggetto statistiche specifico</span><span class="sxs-lookup"><span data-stu-id="50789-130">To update a specific statistics object</span></span>  
  
1.  <span data-ttu-id="50789-131">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50789-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="50789-132">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="50789-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="50789-133">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="50789-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example updates the statistics for the AK_SalesOrderDetail_rowguid index of the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail AK_SalesOrderDetail_rowguid;   
    GO  
    ```  
  
#### <a name="to-update-all-statistics-in-a-table"></a><span data-ttu-id="50789-134">Per aggiornare tutte le statistiche in una tabella</span><span class="sxs-lookup"><span data-stu-id="50789-134">To update all statistics in a table</span></span>  
  
1.  <span data-ttu-id="50789-135">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50789-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="50789-136">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="50789-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="50789-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="50789-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all indexes on the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail;   
    GO  
    ```  
  
 <span data-ttu-id="50789-138">Per altre informazioni, vedere [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50789-138">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
#### <a name="to-update-all-statistics-in-a-database"></a><span data-ttu-id="50789-139">Per aggiornare tutte le statistiche in un database</span><span class="sxs-lookup"><span data-stu-id="50789-139">To update all statistics in a database</span></span>  
  
1.  <span data-ttu-id="50789-140">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50789-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="50789-141">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="50789-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="50789-142">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="50789-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all tables in the database.   
    EXEC sp_updatestats;  
    ```  
  
 <span data-ttu-id="50789-143">Per altre informazioni, vedere [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50789-143">For more information, see [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span></span>  
  
  
