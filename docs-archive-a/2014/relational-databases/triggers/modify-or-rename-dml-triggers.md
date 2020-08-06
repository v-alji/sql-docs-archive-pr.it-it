---
title: Modificare o rinominare trigger DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- renaming triggers
- modifying triggers
- DML triggers, modifying
ms.assetid: c7317eec-c0e9-479e-a4a7-83b6b6c58d59
author: rothja
ms.author: jroth
ms.openlocfilehash: 65bb13552b552d54b5547eadedc412977e423a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637127"
---
# <a name="modify-or-rename-dml-triggers"></a><span data-ttu-id="73f83-102">Modifica o ridenominazione di trigger DML</span><span class="sxs-lookup"><span data-stu-id="73f83-102">Modify or Rename DML Triggers</span></span>
  <span data-ttu-id="73f83-103">In questo argomento viene illustrato come modificare o rinominare un trigger DML in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73f83-103">This topic describes how to modify or rename a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="73f83-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="73f83-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="73f83-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="73f83-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="73f83-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="73f83-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="73f83-107">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="73f83-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="73f83-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="73f83-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="73f83-109">**Per modificare o rinominare un trigger DML utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="73f83-109">**To modify or rename a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="73f83-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="73f83-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="73f83-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="73f83-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="73f83-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="73f83-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="73f83-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="73f83-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="73f83-114">Quando si rinomina un trigger, il trigger deve trovarsi nel database corrente e il nuovo nome deve seguire le regole per gli [identificatori](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="73f83-114">When you rename a trigger, the trigger must be in the current database, and the new name must follow the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="73f83-115">Raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="73f83-115">Recommendations</span></span>  
  
-   <span data-ttu-id="73f83-116">È consigliabile non usare la stored procedure [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) per rinominare un trigger.</span><span class="sxs-lookup"><span data-stu-id="73f83-116">We recommend you do not use the [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) stored procedure to rename a trigger.</span></span> <span data-ttu-id="73f83-117">La modifica di una parte del nome di un oggetto potrebbe compromettere il funzionamento di script e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="73f83-117">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="73f83-118">La ridenominazione di un trigger non comporta la modifica del nome dell'oggetto corrispondente nella colonna di definizione della vista del catalogo [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="73f83-118">Renaming a trigger does not change the name of the corresponding object name in the definition column of the [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) catalog view.</span></span> <span data-ttu-id="73f83-119">È consigliabile eliminare e ricreare il trigger.</span><span class="sxs-lookup"><span data-stu-id="73f83-119">We recommend that you drop and re-create the trigger instead.</span></span>  
  
-   <span data-ttu-id="73f83-120">Se si modifica il nome di un oggetto a cui fa riferimento un trigger DML, è necessario modificare il trigger in modo che il testo corrisponda al nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="73f83-120">If you change the name of an object referenced by a DML trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="73f83-121">Pertanto, prima di rinominare un oggetto, visualizzare le dipendenze dell'oggetto per determinare se la modifica proposta interessa i trigger.</span><span class="sxs-lookup"><span data-stu-id="73f83-121">Therefore, before you rename an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
-   <span data-ttu-id="73f83-122">È inoltre possibile rinominare i trigger DML per crittografarne la definizione.</span><span class="sxs-lookup"><span data-stu-id="73f83-122">A DML trigger can also be modified to encrypt its definition.</span></span>  
  
-   <span data-ttu-id="73f83-123">Per visualizzare le dipendenze di un trigger, è possibile utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o la funzione e viste del catalogo seguenti:</span><span class="sxs-lookup"><span data-stu-id="73f83-123">To view the dependencies of a trigger, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the following function and catalog views:</span></span>  
  
    -   [<span data-ttu-id="73f83-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73f83-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
    -   [<span data-ttu-id="73f83-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73f83-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
    -   [<span data-ttu-id="73f83-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73f83-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="73f83-127">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="73f83-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="73f83-128">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="73f83-128">Permissions</span></span>  
 <span data-ttu-id="73f83-129">Per modificare un trigger DML è necessaria l'autorizzazione ALTER sulla tabella o vista in cui è definito il trigger.</span><span class="sxs-lookup"><span data-stu-id="73f83-129">To alter a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="73f83-130">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="73f83-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-dml-trigger"></a><span data-ttu-id="73f83-131">Per modificare un trigger DML</span><span class="sxs-lookup"><span data-stu-id="73f83-131">To modify a DML trigger</span></span>  
  
1.  <span data-ttu-id="73f83-132">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="73f83-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="73f83-133">Espandere il database desiderato, espandere **Tabelle**, quindi espandere la tabella che contiene il trigger da modificare.</span><span class="sxs-lookup"><span data-stu-id="73f83-133">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to modify.</span></span>  
  
3.  <span data-ttu-id="73f83-134">Espandere **Trigger**, fare clic con il pulsante destro del mouse sul trigger da modificare, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="73f83-134">Expand **Triggers**, right-click the trigger to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="73f83-135">Modificare il trigger e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="73f83-135">Modify the trigger, and then click **Execute**.</span></span>  
  
#### <a name="to-rename-a-dml-trigger"></a><span data-ttu-id="73f83-136">Per rinominare un trigger DML</span><span class="sxs-lookup"><span data-stu-id="73f83-136">To rename a DML trigger</span></span>  
  
1.  <span data-ttu-id="73f83-137">[Eliminare il trigger](../triggers/dml-triggers.md) che si desidera rinominare.</span><span class="sxs-lookup"><span data-stu-id="73f83-137">[Delete the trigger](../triggers/dml-triggers.md) that you want to rename.</span></span>  
  
2.  <span data-ttu-id="73f83-138">[Ricreare il trigger](../triggers/create-dml-triggers.md), specificando il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="73f83-138">[Re-create the trigger](../triggers/create-dml-triggers.md), specifying the new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="73f83-139">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="73f83-139">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-trigger-using-alter-trigger"></a><span data-ttu-id="73f83-140">Per modificare un trigger utilizzando ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="73f83-140">To modify a trigger using ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="73f83-141">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73f83-141">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="73f83-142">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="73f83-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="73f83-143">Copiare e incollare gli esempi seguenti nella query.</span><span class="sxs-lookup"><span data-stu-id="73f83-143">Copy and paste the following examples into the query.</span></span> <span data-ttu-id="73f83-144">Eseguire il primo esempio per creare un trigger DML per la stampa di un messaggio definito dall'utente nel client quando un utente tenta di aggiungere o modificare i dati delle modifiche nella tabella `SalesPersonQuotaHistory` .</span><span class="sxs-lookup"><span data-stu-id="73f83-144">Execute the first example to create a DML trigger that prints a user-defined message to the client when a user tries to add or change data in the `SalesPersonQuotaHistory` table.</span></span> <span data-ttu-id="73f83-145">Eseguire l'istruzione [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) per modificare il trigger in modo che venga attivato solo con le attività `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="73f83-145">Execute the [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statement to modify the trigger to fire only on `INSERT` activities.</span></span> <span data-ttu-id="73f83-146">Questo trigger risulta molto utile, in quanto ricorda all'utente che aggiorna o inserisce righe nella tabella di inviare una notifica al reparto `Compensation` .</span><span class="sxs-lookup"><span data-stu-id="73f83-146">This trigger is helpful because it reminds the user that updates or inserts rows into this table to also notify the `Compensation` department.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
USE AdventureWorks2012;  
GO  
ALTER TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
AFTER INSERT  
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
#### <a name="to-rename-a-trigger-using-drop-trigger-and-alter-trigger"></a><span data-ttu-id="73f83-147">Per rinominare un trigger utilizzando DROP TRIGGER e ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="73f83-147">To rename a trigger using DROP TRIGGER and ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="73f83-148">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73f83-148">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="73f83-149">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="73f83-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="73f83-150">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="73f83-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="73f83-151">In questo esempio vengono utilizzate le istruzioni [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) e [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) per rinominare il trigger `Sales.bonus_reminder` in `Sales.bonus_reminder_2`.</span><span class="sxs-lookup"><span data-stu-id="73f83-151">This example use the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) and [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statements to rename the `Sales.bonus_reminder` trigger to `Sales.bonus_reminder_2`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder_2  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="73f83-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73f83-152">See Also</span></span>  
 <span data-ttu-id="73f83-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="73f83-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="73f83-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="73f83-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="73f83-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="73f83-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="73f83-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="73f83-160">[Ottieni informazioni sui trigger DML](../triggers/get-information-about-dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="73f83-160">[Get Information About DML Triggers](../triggers/get-information-about-dml-triggers.md) </span></span>  
 <span data-ttu-id="73f83-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="73f83-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="73f83-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="73f83-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="73f83-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="73f83-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="73f83-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="73f83-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="73f83-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73f83-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="73f83-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73f83-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
