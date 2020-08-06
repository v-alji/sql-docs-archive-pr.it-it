---
title: Modificare i dati tramite una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- data modifications [SQL Server], views
- views [SQL Server], modifying data through
- modifying data [SQL Server], views
ms.assetid: 410e2812-4ebe-48b2-b95f-c7784f1c4336
author: stevestein
ms.author: sstein
ms.openlocfilehash: df1eb4a33d1d10e63363e52760dad805b20c0a8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623963"
---
# <a name="modify-data-through-a-view"></a><span data-ttu-id="94c5a-102">Modificare i dati tramite una vista</span><span class="sxs-lookup"><span data-stu-id="94c5a-102">Modify Data Through a View</span></span>
  <span data-ttu-id="94c5a-103">È possibile modificare i dati di una tabella di base sottostante in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94c5a-103">You can modify the data of an underlying base table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="94c5a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="94c5a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="94c5a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="94c5a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="94c5a-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="94c5a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="94c5a-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="94c5a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="94c5a-108">**Per modificare i dati della tabella tramite una vista utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="94c5a-108">**To modify table data through a view, using:**</span></span>  
  
     [<span data-ttu-id="94c5a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94c5a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="94c5a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94c5a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="94c5a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="94c5a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="94c5a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="94c5a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="94c5a-113">Vedere la sezione "Viste aggiornabili" in [CREATE VIEW & #40; Transact-SQL & #41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94c5a-113">See the section 'Updatable Views' in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="94c5a-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="94c5a-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="94c5a-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="94c5a-115">Permissions</span></span>  
 <span data-ttu-id="94c5a-116">È richiesta l'autorizzazione UPDATE, INSERT o DELETE per la tabella di destinazione, a seconda dell'azione eseguita.</span><span class="sxs-lookup"><span data-stu-id="94c5a-116">Requires UPDATE, INSERT, or DELETE permissions on the target table, depending on the action being performed.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="94c5a-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94c5a-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-table-data-through-a-view"></a><span data-ttu-id="94c5a-118">Per modificare i dati della tabella tramite una vista</span><span class="sxs-lookup"><span data-stu-id="94c5a-118">To modify table data through a view</span></span>  
  
1.  <span data-ttu-id="94c5a-119">In **Esplora oggetti**espandere il database contenente la vista, quindi espandere **Viste**.</span><span class="sxs-lookup"><span data-stu-id="94c5a-119">In **Object Explorer**, expand the database that contains the view and then expand **Views**.</span></span>  
  
2.  <span data-ttu-id="94c5a-120">Fare clic con il pulsante destro del mouse sulla vista e selezionare **Modifica le prime 200 righe**.</span><span class="sxs-lookup"><span data-stu-id="94c5a-120">Right-click the view and select **Edit Top 200 Rows**.</span></span>  
  
3.  <span data-ttu-id="94c5a-121">È possibile che sia necessario modificare l'istruzione SELECT nel riquadro **SQL** affinché vengano restituite le righe da modificare.</span><span class="sxs-lookup"><span data-stu-id="94c5a-121">You may need to modify the SELECT statement in the **SQL** pane to return the rows to be modified.</span></span>  
  
4.  <span data-ttu-id="94c5a-122">Nel riquadro dei **risultati** individuare la riga da modificare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="94c5a-122">In the **Results** pane, locate the row to be changed or deleted.</span></span> <span data-ttu-id="94c5a-123">Per eliminare la riga, fare clic con il pulsante destro del mouse sulla riga e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="94c5a-123">To delete the row, right-click the row and select **Delete**.</span></span> <span data-ttu-id="94c5a-124">Per modificare i dati in una o più colonne, modificare i dati nella colonna.</span><span class="sxs-lookup"><span data-stu-id="94c5a-124">To change data in one or more columns, modify the data in the column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="94c5a-125">Non è possibile eliminare una riga se la vista fa riferimento a più di una tabella di base.</span><span class="sxs-lookup"><span data-stu-id="94c5a-125">You cannot delete a row if the view references more than one base table.</span></span> <span data-ttu-id="94c5a-126">È possibile aggiornare solo le colonne che appartengono a una singola tabella di base.</span><span class="sxs-lookup"><span data-stu-id="94c5a-126">You can only update columns that belong to a single base table.</span></span>  
  
5.  <span data-ttu-id="94c5a-127">Per inserire una riga, scorrere fino alla fine delle righe e inserire i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="94c5a-127">To insert a row, scroll down to the end of the rows and insert the new values.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="94c5a-128">Non è possibile inserire una riga se la vista fa riferimento a più di una tabella di base.</span><span class="sxs-lookup"><span data-stu-id="94c5a-128">You cannot insert a row if the view references more than one base table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="94c5a-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94c5a-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-table-data-through-a-view"></a><span data-ttu-id="94c5a-130">Per aggiornare i dati della tabella tramite una vista</span><span class="sxs-lookup"><span data-stu-id="94c5a-130">To update table data through a view</span></span>  
  
1.  <span data-ttu-id="94c5a-131">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94c5a-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="94c5a-132">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="94c5a-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="94c5a-133">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="94c5a-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="94c5a-134">In questo esempio si modifica il valore nelle colonne `StartDate` e `EndDate` per un dipendente specifico facendo riferimento alle colonne nella vista `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="94c5a-134">This example changes the value in the `StartDate` and `EndDate` columns for a specific employee by referencing columns in the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="94c5a-135">Tramite questa vista vengono restituiti valori da due tabelle.</span><span class="sxs-lookup"><span data-stu-id="94c5a-135">This view returns values from two tables.</span></span> <span data-ttu-id="94c5a-136">Questa istruzione viene completata perché le colonne modificate provengono solo da una delle tabelle di base.</span><span class="sxs-lookup"><span data-stu-id="94c5a-136">This statement succeeds because the columns being modified are from only one of the base tables.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    UPDATE HumanResources.vEmployeeDepartmentHistory  
    SET StartDate = '20110203', EndDate = GETDATE()   
    WHERE LastName = N'Smith' AND FirstName = 'Samantha';   
    GO  
    ```  
  
 <span data-ttu-id="94c5a-137">Per altre informazioni, vedere [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94c5a-137">For more information, see [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span></span>  
  
#### <a name="to-insert-table-data-through-a-view"></a><span data-ttu-id="94c5a-138">Per inserire i dati della tabella tramite una vista</span><span class="sxs-lookup"><span data-stu-id="94c5a-138">To insert table data through a view</span></span>  
  
1.  <span data-ttu-id="94c5a-139">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94c5a-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="94c5a-140">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="94c5a-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="94c5a-141">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="94c5a-141">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="94c5a-142">Nell'esempio si inserisce una nuova riga nella tabella di base `HumanResouces.Department` specificando le relative colonne dalla vista `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="94c5a-142">The example inserts a new row into the base table `HumanResouces.Department` by specifying the relevant columns from the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="94c5a-143">L'istruzione viene completata perché sono specificate solo colonne di una singola tabella di base mentre le altre colonne in questa tabella dispongono di valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="94c5a-143">The statement succeeds because only columns from a single base table are specified and the other columns in the base table have default values.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    INSERT INTO HumanResources.vEmployeeDepartmentHistory (Department, GroupName)   
    VALUES ('MyDepartment', 'MyGroup');   
    GO  
    ```  
  
 <span data-ttu-id="94c5a-144">Per altre informazioni, vedere [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94c5a-144">For more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span></span>  
  
  
