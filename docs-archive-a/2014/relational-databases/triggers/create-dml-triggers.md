---
title: Creare trigger DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], DML triggers
- deferred name resolution, DML triggers
- WITH ENCRYPTION clause
- IF UPDATE
- SET statement, DML triggers
- DML triggers, programming
- testing column changes
- results [SQL Server], DML triggers
ms.assetid: b2b52258-642b-462e-8e0f-18c09d2eccf4
author: rothja
ms.author: jroth
ms.openlocfilehash: f843513ba634bcb3479e373eb9ac978ab584588d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637147"
---
# <a name="create-dml-triggers"></a><span data-ttu-id="8ecbf-102">Creare trigger DML.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-102">Create DML Triggers</span></span>
  <span data-ttu-id="8ecbf-103">Questo argomento illustra come creare un trigger DML [!INCLUDE[tsql](../../includes/tsql-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] DML trigger by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement.</span></span>  
  
##  <a name="before-you-begin"></a><a name="Top"></a> <span data-ttu-id="8ecbf-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8ecbf-104">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="8ecbf-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8ecbf-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8ecbf-106">Per un elenco di limitazioni e restrizioni associate alla creazione di trigger DML, vedere [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ecbf-106">For a list of limitations and restrictions related to creating DML triggers, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ecbf-107">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8ecbf-107">Permissions</span></span>  
 <span data-ttu-id="8ecbf-108">È necessario disporre dell'autorizzazione ALTER per la tabella o la vista in cui si desidera creare il trigger.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-108">Requires ALTER permission on the table or view on which the trigger is being created.</span></span>  
  
##  <a name="how-to-create-a-dml-trigger"></a><a name="Procedures"></a> <span data-ttu-id="8ecbf-109">Procedura: Creazione di un trigger DML</span><span class="sxs-lookup"><span data-stu-id="8ecbf-109">How to Create a DML Trigger</span></span>  
 <span data-ttu-id="8ecbf-110">È possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="8ecbf-110">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="8ecbf-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ecbf-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="8ecbf-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ecbf-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8ecbf-113">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ecbf-113">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8ecbf-114">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8ecbf-115">Espandere **Database**, espandere il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , espandere **Tabelle** e quindi espandere la tabella **Purchasing.PurchaseOrderHeader**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, expand **Tables** and then expand the table **Purchasing.PurchaseOrderHeader**.</span></span>  
  
3.  <span data-ttu-id="8ecbf-116">Fare clic con il pulsante destro del mouse su **Trigger**, quindi scegliere **Nuovo trigger**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-116">Right-click **Triggers**, and then select **New Trigger**.</span></span>  
  
4.  <span data-ttu-id="8ecbf-117">Scegliere **Imposta valori per parametri modello** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span> <span data-ttu-id="8ecbf-118">In alternativa, è possibile premere (CTRL+MAIUSC+M) per aprire la finestra di dialogo **Imposta valori per parametri modello** .</span><span class="sxs-lookup"><span data-stu-id="8ecbf-118">Alternatively, you can press (Ctrl-Shift-M) to open the **Specify Values for Template Parameters** dialog box.</span></span>  
  
5.  <span data-ttu-id="8ecbf-119">Nella finestra di dialogo **Imposta valori per parametri modello** immettere i seguenti valori per i parametri indicati.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-119">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="8ecbf-120">Parametro</span><span class="sxs-lookup"><span data-stu-id="8ecbf-120">Parameter</span></span>|<span data-ttu-id="8ecbf-121">valore</span><span class="sxs-lookup"><span data-stu-id="8ecbf-121">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="8ecbf-122">Autore</span><span class="sxs-lookup"><span data-stu-id="8ecbf-122">Author</span></span>|<span data-ttu-id="8ecbf-123">*Nome dell'utente*</span><span class="sxs-lookup"><span data-stu-id="8ecbf-123">*Your name*</span></span>|  
    |<span data-ttu-id="8ecbf-124">Data di creazione</span><span class="sxs-lookup"><span data-stu-id="8ecbf-124">Create Date</span></span>|<span data-ttu-id="8ecbf-125">*Data corrente*</span><span class="sxs-lookup"><span data-stu-id="8ecbf-125">*Today's date*</span></span>|  
    |<span data-ttu-id="8ecbf-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ecbf-126">Description</span></span>|<span data-ttu-id="8ecbf-127">Prima di consentire un nuovo ordine di acquisto con il fornitore da inserire, viene controllata la posizione finanziaria del fornitore.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-127">Checks the vendor credit rating before allowing a new purchase order with the vendor to be inserted.</span></span>|  
    |<span data-ttu-id="8ecbf-128">Schema_Name</span><span class="sxs-lookup"><span data-stu-id="8ecbf-128">Schema_Name</span></span>|<span data-ttu-id="8ecbf-129">Acquisto</span><span class="sxs-lookup"><span data-stu-id="8ecbf-129">Purchasing</span></span>|  
    |<span data-ttu-id="8ecbf-130">Trigger_Name</span><span class="sxs-lookup"><span data-stu-id="8ecbf-130">Trigger_Name</span></span>|<span data-ttu-id="8ecbf-131">NewPODetail2</span><span class="sxs-lookup"><span data-stu-id="8ecbf-131">NewPODetail2</span></span>|  
    |<span data-ttu-id="8ecbf-132">Table_Name</span><span class="sxs-lookup"><span data-stu-id="8ecbf-132">Table_Name</span></span>|<span data-ttu-id="8ecbf-133">PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="8ecbf-133">PurchaseOrderDetail</span></span>|  
    |<span data-ttu-id="8ecbf-134">Data_Modification_Statement</span><span class="sxs-lookup"><span data-stu-id="8ecbf-134">Data_Modification_Statement</span></span>|<span data-ttu-id="8ecbf-135">Consente di rimuovere UPDATE e DELETE dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-135">Remove UPDATE and DELETE from the list.</span></span>|  
  
6.  <span data-ttu-id="8ecbf-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-136">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="8ecbf-137">Nell' **Editor di query**sostituire il commento `-- Insert statements for trigger here` con l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="8ecbf-137">In the **Query Editor**, replace the comment `-- Insert statements for trigger here` with the following statement:</span></span>  
  
    ```sql  
    IF @@ROWCOUNT = 1  
    BEGIN  
       UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal + LineTotal  
       FROM inserted  
       WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
  
    END  
    ELSE  
    BEGIN  
          UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal +   
          (SELECT SUM(LineTotal)  
          FROM inserted  
          WHERE PurchaseOrderHeader.PurchaseOrderID  
           = inserted.PurchaseOrderID)  
       WHERE PurchaseOrderHeader.PurchaseOrderID IN  
          (SELECT PurchaseOrderID FROM inserted)  
    END;  
    ```  
  
8.  <span data-ttu-id="8ecbf-138">Per verificare la validità della sintassi, scegliere **Analizza** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-138">To verify the syntax is valid, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="8ecbf-139">Se viene restituito un messaggio di errore, confrontare l'istruzione con le informazioni precedenti, apportare le modifiche necessarie e ripetere il passaggio.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-139">If an error message is returned, compare the statement with the information above and correct as needed and repeat this step.</span></span>  
  
9. <span data-ttu-id="8ecbf-140">Per creare il trigger DML, scegliere **Esegui** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-140">To create the DML trigger, from the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="8ecbf-141">Il trigger DML viene creato come un oggetto nel database.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-141">The DML trigger is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="8ecbf-142">Per visualizzare il trigger DML nell'elenco di Esplora oggetti, fare clic con il pulsante destro del mouse su **Trigger** e scegliere **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-142">To see the DML trigger listed in Object Explorer, right-click **Triggers** and select **Refresh**.</span></span>  
  
 [<span data-ttu-id="8ecbf-143">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8ecbf-143">Before You Begin</span></span>](#Top)  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8ecbf-144">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ecbf-144">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="8ecbf-145">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8ecbf-146">Nel menu **File** , fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-146">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8ecbf-147">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8ecbf-148">In questo esempio vengono creati gli stessi trigger DML archiviati indicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8ecbf-148">This example creates the same stored DML trigger as above.</span></span>  
  
    ```sql
    -- Trigger valid for multirow and single row inserts  
    -- and optimal for single row inserts.  
    USE AdventureWorks2012;  
    GO  
    CREATE TRIGGER NewPODetail3  
    ON Purchasing.PurchaseOrderDetail  
    FOR INSERT AS  
    IF @@ROWCOUNT = 1  
    BEGIN  
       UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal + LineTotal  
       FROM inserted  
       WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
  
    END  
    ELSE  
    BEGIN  
          UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal +   
          (SELECT SUM(LineTotal)  
          FROM inserted  
          WHERE PurchaseOrderHeader.PurchaseOrderID  
           = inserted.PurchaseOrderID)  
       WHERE PurchaseOrderHeader.PurchaseOrderID IN  
          (SELECT PurchaseOrderID FROM inserted)  
    END;  
    ```  
