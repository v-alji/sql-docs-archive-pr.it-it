---
title: Creare trigger annidati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- recursive DML triggers [SQL Server]
- DML triggers, nested
- triggers [SQL Server], nested
- direct recursion [SQL Server]
- triggers [SQL Server], recursive
- DML triggers, recursive
- RECURSIVE_TRIGGERS option
- indirect recursion [SQL Server]
- nested DML triggers
ms.assetid: cd522dda-b4ab-41b8-82b0-02445bdba7af
author: rothja
ms.author: jroth
ms.openlocfilehash: c0016fc3cdd93ea78ceed56efa076a01bd85be50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637149"
---
# <a name="create-nested-triggers"></a><span data-ttu-id="4928b-102">Creazione di trigger annidati</span><span class="sxs-lookup"><span data-stu-id="4928b-102">Create Nested Triggers</span></span>
  <span data-ttu-id="4928b-103">Entrambi i trigger DML e DDL vengono nidificati quando un trigger esegue un'operazione che ne avvia un altro.</span><span class="sxs-lookup"><span data-stu-id="4928b-103">Both DML and DDL triggers are nested when a trigger performs an action that initiates another trigger.</span></span> <span data-ttu-id="4928b-104">Tali operazioni possono quindi avviare altri trigger e così via.</span><span class="sxs-lookup"><span data-stu-id="4928b-104">These actions can initiate other triggers, and so on.</span></span> <span data-ttu-id="4928b-105">I trigger DML e DDL possono essere nidificati fino a un massimo di 32 livelli.</span><span class="sxs-lookup"><span data-stu-id="4928b-105">DML and DDL triggers can be nested up to 32 levels.</span></span> <span data-ttu-id="4928b-106">Per gestire la nidificazione dei trigger AFTER, utilizzare l'opzione di configurazione del server **nested triggers** .</span><span class="sxs-lookup"><span data-stu-id="4928b-106">You can control whether AFTER triggers can be nested through the **nested triggers** server configuration option.</span></span> <span data-ttu-id="4928b-107">I trigger INSTEAD OF (solo DML) possono essere nidificati indipendentemente da questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="4928b-107">INSTEAD OF triggers (only DML triggers can be INSTEAD OF triggers) can be nested regardless of this setting.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4928b-108">Qualsiasi riferimento a codice gestito da un trigger [!INCLUDE[tsql](../../includes/tsql-md.md)] viene conteggiato come un unico livello rispetto al limite dei 32 livelli di nidificazione.</span><span class="sxs-lookup"><span data-stu-id="4928b-108">Any reference to managed code from a [!INCLUDE[tsql](../../includes/tsql-md.md)] trigger counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="4928b-109">I metodi richiamati da codice gestito non vengono inclusi nel conteggio per questo limite.</span><span class="sxs-lookup"><span data-stu-id="4928b-109">Methods invoked from within managed code do not count against this limit.</span></span>  
  
 <span data-ttu-id="4928b-110">Se è consentito l'utilizzo di trigger nidificati e un trigger della catena avvia un ciclo infinito, il livello di nidificazione viene superato e il trigger viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="4928b-110">If nested triggers are allowed and a trigger in the chain starts an infinite loop, the nesting level is exceeded and the trigger terminates.</span></span>  
  
 <span data-ttu-id="4928b-111">È possibile utilizzare i trigger nidificati per eseguire funzioni di manutenzione, utili quali l'archiviazione di una copia di backup delle righe interessate da un trigger precedente.</span><span class="sxs-lookup"><span data-stu-id="4928b-111">You can use nested triggers to perform useful housekeeping functions such as storing a backup copy of rows affected by a previous trigger.</span></span> <span data-ttu-id="4928b-112">È ad esempio possibile creare un trigger su `PurchaseOrderDetail` per salvare una copia di backup delle righe di `PurchaseOrderDetail` eliminate dal trigger `delcascadetrig` .</span><span class="sxs-lookup"><span data-stu-id="4928b-112">For example, you can create a trigger on `PurchaseOrderDetail` that saves a backup copy of the `PurchaseOrderDetail` rows that the `delcascadetrig` trigger deleted.</span></span> <span data-ttu-id="4928b-113">Se il trigger `delcascadetrig` è attivo, l'eliminazione di `PurchaseOrderID` 1965 dalla tabella `PurchaseOrderHeader` implica l'eliminazione della riga o delle righe corrispondenti da `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="4928b-113">With the `delcascadetrig` trigger in effect, deleting `PurchaseOrderID` 1965 from `PurchaseOrderHeader` deletes the corresponding row or rows from `PurchaseOrderDetail`.</span></span> <span data-ttu-id="4928b-114">Per salvare i dati eliminati in un'altra tabella creata separatamente denominata `PurchaseOrderDetail` , creare un trigger DELETE su `del_save`.</span><span class="sxs-lookup"><span data-stu-id="4928b-114">To save the data, you can create a DELETE trigger on `PurchaseOrderDetail` that saves the deleted data into another separately created table, `del_save`.</span></span> <span data-ttu-id="4928b-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4928b-115">For example:</span></span>  
  
```  
CREATE TRIGGER Purchasing.savedel  
   ON Purchasing.PurchaseOrderDetail  
FOR DELETE  
AS  
   INSERT del_save;  
   SELECT * FROM deleted;  
```  
  
 <span data-ttu-id="4928b-116">È consigliabile non utilizzare trigger nidificati in una sequenza dipendente dall'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="4928b-116">We do not recommend using nested triggers in an order-dependent sequence.</span></span> <span data-ttu-id="4928b-117">Utilizzare trigger distinti per eseguire modifiche a catena dei dati.</span><span class="sxs-lookup"><span data-stu-id="4928b-117">Use separate triggers to cascade data modifications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4928b-118">Poiché i trigger vengono eseguiti all'interno di una transazione, un errore a qualsiasi livello di un set di trigger nidificati annulla l'intera transazione con conseguente rollback di tutte le modifiche apportate ai dati.</span><span class="sxs-lookup"><span data-stu-id="4928b-118">Because triggers execute within a transaction, a failure at any level of a set of nested triggers cancels the entire transaction, and all data modifications are rolled back.</span></span> <span data-ttu-id="4928b-119">Per determinare la posizione in cui si è verificato l'errore, includere nei trigger le istruzioni PRINT.</span><span class="sxs-lookup"><span data-stu-id="4928b-119">Include PRINT statements in your triggers so that you can determine where the failure has occurred.</span></span>  
  
## <a name="recursive-triggers"></a><span data-ttu-id="4928b-120">Trigger ricorsivi</span><span class="sxs-lookup"><span data-stu-id="4928b-120">Recursive Triggers</span></span>  
 <span data-ttu-id="4928b-121">Un trigger AFTER non chiama se stesso in modo ricorsivo a meno che non sia stata impostata l'opzione di database RECURSIVE_TRIGGERS.</span><span class="sxs-lookup"><span data-stu-id="4928b-121">An AFTER trigger does not call itself recursively unless the RECURSIVE_TRIGGERS database option is set.</span></span>  
  
 <span data-ttu-id="4928b-122">Esistono due tipi di ricorsione:</span><span class="sxs-lookup"><span data-stu-id="4928b-122">There are two types of recursion:</span></span>  
  
-   <span data-ttu-id="4928b-123">Ricorsione diretta</span><span class="sxs-lookup"><span data-stu-id="4928b-123">Direct recursion</span></span>  
  
     <span data-ttu-id="4928b-124">Questo tipo di ricorsione si verifica quando un trigger viene attivato ed esegue un'azione che attiva nuovamente lo stesso trigger.</span><span class="sxs-lookup"><span data-stu-id="4928b-124">This recursion occurs when a trigger fires and performs an action that causes the same trigger to fire again.</span></span> <span data-ttu-id="4928b-125">Ad esempio, un'applicazione aggiorna la tabella **T3**che attiva il trigger **Trig3** .</span><span class="sxs-lookup"><span data-stu-id="4928b-125">For example, an application updates table **T3**; this causes trigger **Trig3** to fire.</span></span> <span data-ttu-id="4928b-126">**Trig3** aggiorna nuovamente la tabella **T3** , che attiva nuovamente il trigger **Trig3** .</span><span class="sxs-lookup"><span data-stu-id="4928b-126">**Trig3** updates table **T3** again; this causes trigger **Trig3** to fire again.</span></span>  
  
     <span data-ttu-id="4928b-127">La ricorsione diretta può inoltre verificarsi quando lo stesso trigger viene richiamato, ma solo dopo la chiamata di un trigger di tipo diverso (AFTER o INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="4928b-127">Direct recursion can also occur when the same trigger is called again, but after a trigger of a different type (AFTER or INSTEAD OF) is called.</span></span> <span data-ttu-id="4928b-128">In altri termini, la ricorsione diretta di un trigger INSTEAD OF può verificarsi quando lo stesso trigger INSTEAD OF viene chiamato per la seconda volta, anche se nel frattempo sono stati chiamati uno o più trigger AFTER.</span><span class="sxs-lookup"><span data-stu-id="4928b-128">In other words, direct recursion of an INSTEAD OF trigger can occur when the same INSTEAD OF trigger is called for a second time, even if one or more AFTER triggers are called in between.</span></span> <span data-ttu-id="4928b-129">Analogamente, la ricorsione diretta di un trigger AFTER può verificarsi quando lo stesso trigger AFTER viene chiamato per la seconda volta, anche se nel frattempo sono stati chiamati uno o più trigger INSTEAD OF.</span><span class="sxs-lookup"><span data-stu-id="4928b-129">Likewise, direct recursion of an AFTER trigger can occur when the same AFTER trigger is called for a second time, even if one or more INSTEAD OF triggers are called in between.</span></span> <span data-ttu-id="4928b-130">Ad esempio, un'applicazione aggiorna la tabella **T4**.</span><span class="sxs-lookup"><span data-stu-id="4928b-130">For example, an application updates table **T4**.</span></span> <span data-ttu-id="4928b-131">L'aggiornamento attiva il trigger INSTEAD OF **Trig4** .</span><span class="sxs-lookup"><span data-stu-id="4928b-131">This update causes INSTEAD OF trigger **Trig4** to fire.</span></span> <span data-ttu-id="4928b-132">**Trig4** aggiorna la tabella **T5**.</span><span class="sxs-lookup"><span data-stu-id="4928b-132">**Trig4** updates table **T5**.</span></span> <span data-ttu-id="4928b-133">L'aggiornamento attiva il trigger AFTER **Trig5** .</span><span class="sxs-lookup"><span data-stu-id="4928b-133">This update causes AFTER trigger **Trig5** to fire.</span></span> <span data-ttu-id="4928b-134">**Trig5** aggiorna la tabella **T4**e questa operazione attiva nuovamente il trigger INSTEAD OF **Trig4** .</span><span class="sxs-lookup"><span data-stu-id="4928b-134">**Trig5** updates table **T4**, and this update causes INSTEAD OF trigger **Trig4** to fire again.</span></span> <span data-ttu-id="4928b-135">Questa catena di eventi costituisce una ricorsione diretta per il trigger **Trig4**.</span><span class="sxs-lookup"><span data-stu-id="4928b-135">This chain of events is considered direct recursion for **Trig4**.</span></span>  
  
-   <span data-ttu-id="4928b-136">Ricorsione indiretta</span><span class="sxs-lookup"><span data-stu-id="4928b-136">Indirect recursion</span></span>  
  
     <span data-ttu-id="4928b-137">Questo tipo di ricorsione si verifica quando un trigger viene attivato ed esegue un'azione che attiva un altro trigger dello stesso tipo (AFTER o INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="4928b-137">This recursion occurs when a trigger fires and performs an action that causes another trigger of the same type (AFTER or INSTEAD OF) to fire.</span></span> <span data-ttu-id="4928b-138">Il secondo esegue un'operazione che implica nuovamente l'attivazione del trigger originale.</span><span class="sxs-lookup"><span data-stu-id="4928b-138">This second trigger performs an action that causes the original trigger to fire again.</span></span> <span data-ttu-id="4928b-139">In altri termini, la ricorsione indiretta può verificarsi quando un trigger INSTEAD OF viene chiamato per la seconda volta, ma non prima della chiamata di un altro trigger INSTEAD OF.</span><span class="sxs-lookup"><span data-stu-id="4928b-139">In other words, indirect recursion can occur when an INSTEAD OF trigger is called for a second time, but not until another INSTEAD OF trigger is called in between.</span></span> <span data-ttu-id="4928b-140">Analogamente, la ricorsione indiretta può verificarsi quando un trigger AFTER viene chiamato per la seconda volta, ma non prima della chiamata di un altro trigger AFTER.</span><span class="sxs-lookup"><span data-stu-id="4928b-140">Likewise, indirect recursion can occur when an AFTER trigger is called for a second time, but not until another AFTER trigger is called in between.</span></span> <span data-ttu-id="4928b-141">Ad esempio, un'applicazione aggiorna la tabella **T1**.</span><span class="sxs-lookup"><span data-stu-id="4928b-141">For example, an application updates table **T1**.</span></span> <span data-ttu-id="4928b-142">L'aggiornamento attiva il trigger AFTER **Trig1** .</span><span class="sxs-lookup"><span data-stu-id="4928b-142">This update causes AFTER trigger **Trig1** to fire.</span></span> <span data-ttu-id="4928b-143">**Trig1** aggiorna la tabella **T2**e questa operazione attiva il trigger AFTER **Trig2** .</span><span class="sxs-lookup"><span data-stu-id="4928b-143">**Trig1** updates table **T2**, and this update causes AFTER trigger **Trig2** to fire.</span></span> <span data-ttu-id="4928b-144">**Trig2** aggiorna, a sua volta, la tabella **T1** che attiva nuovamente il trigger AFTER **Trig1** .</span><span class="sxs-lookup"><span data-stu-id="4928b-144">**Trig2** in turn updates table **T1** that causes AFTER trigger **Trig1** to fire again.</span></span>  
  
 <span data-ttu-id="4928b-145">Se l'opzione di database RECURSIVE_TRIGGERS è impostata su OFF, viene evitata solo la ricorsione diretta dei trigger AFTER.</span><span class="sxs-lookup"><span data-stu-id="4928b-145">Only direct recursion of AFTER triggers is prevented when the RECURSIVE_TRIGGERS database option is set to OFF.</span></span> <span data-ttu-id="4928b-146">Per disabilitare la ricorsione indiretta dei trigger AFTER, impostare su **0** anche l'opzione del server **nested triggers**.</span><span class="sxs-lookup"><span data-stu-id="4928b-146">To disable indirect recursion of AFTER triggers, also set the **nested triggers** server option to **0**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4928b-147">Esempi</span><span class="sxs-lookup"><span data-stu-id="4928b-147">Examples</span></span>  
 <span data-ttu-id="4928b-148">Nell'esempio seguente viene illustrato l'utilizzo dei trigger ricorsivi per risolvere una relazione autoreferenziale, nota anche come chiusura transitiva.</span><span class="sxs-lookup"><span data-stu-id="4928b-148">The following example shows using recursive triggers to solve a self-referencing relationship (also known as transitive closure).</span></span> <span data-ttu-id="4928b-149">Ad esempio, nella tabella `emp_mgr` vengono definiti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4928b-149">For example, the table `emp_mgr` defines the following:</span></span>  
  
-   <span data-ttu-id="4928b-150">Il dipendente (`emp`) di una società.</span><span class="sxs-lookup"><span data-stu-id="4928b-150">An employee (`emp`) in a company.</span></span>  
  
-   <span data-ttu-id="4928b-151">Il responsabile di ciascun dipendente (`mgr`).</span><span class="sxs-lookup"><span data-stu-id="4928b-151">The manager for each employee (`mgr`).</span></span>  
  
-   <span data-ttu-id="4928b-152">Il numero totale di dipendenti nell'albero organizzativo di cui ogni dipendente è responsabile (`NoOfReports`).</span><span class="sxs-lookup"><span data-stu-id="4928b-152">The total number of employees in the organizational tree reporting to each employee (`NoOfReports`).</span></span>  
  
 <span data-ttu-id="4928b-153">È possibile utilizzare un trigger UPDATE ricorsivo per aggiornare la colonna `NoOfReports` quando vengono inseriti i record di nuovi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4928b-153">A recursive UPDATE trigger can be used to keep the `NoOfReports` column up-to-date as new employee records are inserted.</span></span> <span data-ttu-id="4928b-154">Il trigger INSERT aggiorna la colonna `NoOfReports` del record del responsabile che aggiorna in modo ricorsivo la colonna `NoOfReports` degli altri record fino ai livelli più alti dell'organigramma.</span><span class="sxs-lookup"><span data-stu-id="4928b-154">The INSERT trigger updates the `NoOfReports` column of the manager record, which recursively updates the `NoOfReports` column of other records up the management hierarchy.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Turn recursive triggers ON in the database.  
ALTER DATABASE AdventureWorks2012  
   SET RECURSIVE_TRIGGERS ON;  
GO  
CREATE TABLE dbo.emp_mgr (  
   emp char(30) PRIMARY KEY,  
    mgr char(30) NULL FOREIGN KEY REFERENCES emp_mgr(emp),  
    NoOfReports int DEFAULT 0  
);  
GO  
CREATE TRIGGER dbo.emp_mgrins ON dbo.emp_mgr  
FOR INSERT  
AS  
DECLARE @e char(30), @m char(30);  
DECLARE c1 CURSOR FOR  
   SELECT emp_mgr.emp  
   FROM   emp_mgr, inserted  
   WHERE emp_mgr.emp = inserted.mgr;  
  
OPEN c1;  
FETCH NEXT FROM c1 INTO @e;  
WHILE @@fetch_status = 0  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Add 1 for newly  
   WHERE emp_mgr.emp = @e ;                           -- added employee.  
  
   FETCH NEXT FROM c1 INTO @e;  
END  
CLOSE c1;  
DEALLOCATE c1;  
GO  
-- This recursive UPDATE trigger works assuming:  
--   1. Only singleton updates on emp_mgr.  
--   2. No inserts in the middle of the org tree.  
CREATE TRIGGER dbo.emp_mgrupd ON dbo.emp_mgr FOR UPDATE  
AS  
IF UPDATE (mgr)  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Increment mgr's  
   FROM inserted                            -- (no. of reports) by  
   WHERE emp_mgr.emp = inserted.mgr;         -- 1 for the new report.  
  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports - 1 -- Decrement mgr's  
   FROM deleted                             -- (no. of reports) by 1  
   WHERE emp_mgr.emp = deleted.mgr;          -- for the new report.  
END  
GO  
-- Insert some test data rows.  
INSERT dbo.emp_mgr(emp, mgr) VALUES  
    ('Harry', NULL)  
    ,('Alice', 'Harry')  
    ,('Paul', 'Alice')  
    ,('Joe', 'Alice')  
    ,('Dave', 'Joe');  
GO  
SELECT emp,mgr,NoOfReports  
FROM dbo.emp_mgr;  
GO  
-- Change Dave's manager from Joe to Harry  
UPDATE dbo.emp_mgr SET mgr = 'Harry'  
WHERE emp = 'Dave';  
GO  
SELECT emp,mgr,NoOfReports FROM emp_mgr;  
  
GO  
```  
  
 <span data-ttu-id="4928b-155">Risultati prima dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4928b-155">Here are the results before the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Joe                            0  
Harry                          NULL                           1  
Joe                            Alice                          1  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="4928b-156">Risultati dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4928b-156">Here are the results after the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Harry                          0  
Harry                          NULL                           2  
Joe                            Alice                          0  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="4928b-157">**Per impostare l'opzione nested triggers**</span><span class="sxs-lookup"><span data-stu-id="4928b-157">**To set the nested triggers option**</span></span>  
  
-   [<span data-ttu-id="4928b-158">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4928b-158">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
 <span data-ttu-id="4928b-159">**Per impostare l'opzione di database RECURSIVE_TRIGGERS**</span><span class="sxs-lookup"><span data-stu-id="4928b-159">**To set the RECURSIVE_TRIGGERS database option**</span></span>  
  
-   [<span data-ttu-id="4928b-160">Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4928b-160">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="4928b-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4928b-161">See Also</span></span>  
 <span data-ttu-id="4928b-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4928b-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="4928b-163">Configurare l'opzione di configurazione del server nested triggers</span><span class="sxs-lookup"><span data-stu-id="4928b-163">Configure the nested triggers Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-nested-triggers-server-configuration-option.md)  
  
  
