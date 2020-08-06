---
title: Eliminare statistiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], deleting
- deleting statistics
ms.assetid: eccce0aa-591e-4a1d-bd10-373b022f8749
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 36b74d7e1465c0742cda4fef9f34fb4b3930719c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636628"
---
# <a name="delete-statistics"></a><span data-ttu-id="8be1a-102">Eliminare statistiche</span><span class="sxs-lookup"><span data-stu-id="8be1a-102">Delete Statistics</span></span>
  <span data-ttu-id="8be1a-103">È possibile eliminare statistiche da tabelle e viste in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oppure [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be1a-103">You can delete (drop) statistics from tables and views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="8be1a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8be1a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8be1a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8be1a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8be1a-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8be1a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8be1a-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8be1a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8be1a-108">**Eliminare statistiche da una tabella o una vista tramite:**</span><span class="sxs-lookup"><span data-stu-id="8be1a-108">**To drop statistics from a table or view, using:**</span></span>  
  
     [<span data-ttu-id="8be1a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8be1a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8be1a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8be1a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8be1a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8be1a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8be1a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8be1a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8be1a-113">Eliminare le statistiche con cautela,</span><span class="sxs-lookup"><span data-stu-id="8be1a-113">Be careful when you drop statistics.</span></span> <span data-ttu-id="8be1a-114">in quanto l'operazione può influire sul piano di esecuzione scelto da Query Optimizer.</span><span class="sxs-lookup"><span data-stu-id="8be1a-114">Doing so may affect the execution plan chosen by the query optimizer.</span></span>  
  
-   <span data-ttu-id="8be1a-115">Le statistiche negli indici non possono essere eliminate tramite DROP STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="8be1a-115">Statistics on indexes cannot be dropped by using DROP STATISTICS.</span></span> <span data-ttu-id="8be1a-116">Le statistiche vengono mantenute per tutta l'esistenza dell'indice.</span><span class="sxs-lookup"><span data-stu-id="8be1a-116">Statistics remain as long as the index exists.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8be1a-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8be1a-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8be1a-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8be1a-118">Permissions</span></span>  
 <span data-ttu-id="8be1a-119">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="8be1a-119">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8be1a-120">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8be1a-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="8be1a-121">Per eliminare statistiche da una tabella o una vista</span><span class="sxs-lookup"><span data-stu-id="8be1a-121">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="8be1a-122">In **Esplora oggetti**fare clic sul segno più per espandere il database in cui si desidera eliminare una statistica.</span><span class="sxs-lookup"><span data-stu-id="8be1a-122">In **Object Explorer**, click the plus sign to expand the database in which you want to delete a statistic.</span></span>  
  
2.  <span data-ttu-id="8be1a-123">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="8be1a-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8be1a-124">Fare clic sul segno più per espandere la tabella in cui si desidera eliminare una statistica.</span><span class="sxs-lookup"><span data-stu-id="8be1a-124">Click the plus sign to expand the table in which you want to delete a statistic.</span></span>  
  
4.  <span data-ttu-id="8be1a-125">Fare clic sul segno più per espandere la cartella **Statistiche** .</span><span class="sxs-lookup"><span data-stu-id="8be1a-125">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="8be1a-126">Fare clic con il pulsante destro del mouse sull'oggetto statistiche che si vuole eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8be1a-126">Right-click the statistics object that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="8be1a-127">Nella finestra di dialogo **Elimina oggetto** verificare che sia selezionata la statistica corretta e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8be1a-127">In the **Delete Object** dialog box, ensure that the correct statistic has been selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8be1a-128">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8be1a-128">Using Transact-SQL</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="8be1a-129">Per eliminare statistiche da una tabella o una vista</span><span class="sxs-lookup"><span data-stu-id="8be1a-129">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="8be1a-130">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8be1a-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8be1a-131">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8be1a-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8be1a-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8be1a-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- First, create two statistics named VendorCredit and CustomerTotal  
    -- The first statistic uses a random 50% sample of information provided from the Name and CreditRating columns in the Purchasing.Vendor table.  
    CREATE STATISTICS VendorCredit  
        ON Purchasing.Vendor (Name, CreditRating)  
        WITH SAMPLE 50 PERCENT  
    -- The second statistic uses all of the information from the CustomerID and TotalDue columns in the Sales.SalesOrderHeader table  
    CREATE STATISTICS CustomerTotal  
        ON Sales.SalesOrderHeader (CustomerID, TotalDue)  
        WITH FULLSCAN;  
    GO  
    -- This next statement drops both of the statistics created above. Note that the naming convention is [table_name].[statistics_name].  
    DROP STATISTICS Purchasing.Vendor.VendorCredit, Sales.SalesOrderHeader.CustomerTotal;  
    GO  
    ```  
  
 <span data-ttu-id="8be1a-133">Per altre informazioni, vedere [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8be1a-133">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span></span>  
  
  
