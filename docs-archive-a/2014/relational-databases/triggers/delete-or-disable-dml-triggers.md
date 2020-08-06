---
title: Eliminare o disabilitare trigger DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, disabling
- removing DML triggers
- disabling DML triggers
- dropping DML triggers
- deleting DML triggers
- DML triggers, removing
ms.assetid: 0f97f953-33c5-4b26-afeb-db2a26ce38b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 39b345ade1258987df06938791ac0024e8612365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637144"
---
# <a name="delete-or-disable-dml-triggers"></a><span data-ttu-id="3d72c-102">Eliminare o disabilitare trigger DML</span><span class="sxs-lookup"><span data-stu-id="3d72c-102">Delete or Disable DML Triggers</span></span>
  <span data-ttu-id="3d72c-103">In questo argomento viene descritto come eliminare o disabilitare un trigger DML in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d72c-103">This topic describes how to delete or disable a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3d72c-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3d72c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3d72c-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3d72c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3d72c-106">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="3d72c-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="3d72c-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3d72c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3d72c-108">**Per eliminare o disabilitare un trigger DML tramite:**</span><span class="sxs-lookup"><span data-stu-id="3d72c-108">**To delete or disable a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="3d72c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d72c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3d72c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3d72c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3d72c-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3d72c-111">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3d72c-112">Raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="3d72c-112">Recommendations</span></span>  
  
-   <span data-ttu-id="3d72c-113">Un trigger eliminato viene rimosso dal database corrente,</span><span class="sxs-lookup"><span data-stu-id="3d72c-113">When a trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="3d72c-114">ma la tabella e i dati su cui si basa il trigger non subiscono alcun impatto.</span><span class="sxs-lookup"><span data-stu-id="3d72c-114">The table and the data upon which it is based are not affected.</span></span> <span data-ttu-id="3d72c-115">L'eliminazione di una tabella comporta automaticamente l'eliminazione di tutti i trigger della tabella.</span><span class="sxs-lookup"><span data-stu-id="3d72c-115">Deleting a table automatically deletes any triggers on the table.</span></span>  
  
-   <span data-ttu-id="3d72c-116">Per impostazione predefinita, un trigger viene abilitato quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="3d72c-116">A trigger is enabled by default when it is created.</span></span>  
  
-   <span data-ttu-id="3d72c-117">La disabilitazione di un trigger non ne comporta l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="3d72c-117">Disabling a trigger does not drop it.</span></span> <span data-ttu-id="3d72c-118">Il trigger continua a esistere come oggetto nel database corrente</span><span class="sxs-lookup"><span data-stu-id="3d72c-118">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="3d72c-119">Il trigger, tuttavia, non viene attivato quando viene eseguita qualsiasi istruzione INSERT, UPDATE o DELETE in cui è stato programmato.</span><span class="sxs-lookup"><span data-stu-id="3d72c-119">However, the trigger will not fire when any INSERT, UPDATE, or DELETE statement on which it was programmed is executed.</span></span> <span data-ttu-id="3d72c-120">I trigger disabilitati possono essere riabilitati.</span><span class="sxs-lookup"><span data-stu-id="3d72c-120">Triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="3d72c-121">L'abilitazione di un trigger non comporta la sua creazione ex-novo.</span><span class="sxs-lookup"><span data-stu-id="3d72c-121">Enabling a trigger does not re-create it.</span></span> <span data-ttu-id="3d72c-122">Il trigger viene attivato allo stesso modo in cui è stato creato in origine.</span><span class="sxs-lookup"><span data-stu-id="3d72c-122">The trigger fires in the same manner as when it was originally created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3d72c-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3d72c-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3d72c-124">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3d72c-124">Permissions</span></span>  
 <span data-ttu-id="3d72c-125">Per l'eliminazione di un trigger DML è richiesta l'autorizzazione ALTER per la tabella o la vista in cui è definito il trigger.</span><span class="sxs-lookup"><span data-stu-id="3d72c-125">To delete a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
 <span data-ttu-id="3d72c-126">Per disabilitare o abilitare un trigger DML, è necessario disporre almeno dell'autorizzazione ALTER per la tabella o la vista per cui il trigger è stato creato.</span><span class="sxs-lookup"><span data-stu-id="3d72c-126">To disable or enable a DML trigger, at a minimum, a user must have ALTER permission on the table or view on which the trigger was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3d72c-127">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d72c-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="3d72c-128">Per eliminare un trigger DML</span><span class="sxs-lookup"><span data-stu-id="3d72c-128">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="3d72c-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="3d72c-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3d72c-130">Espandere il database desiderato, espandere **Tabelle**, quindi espandere la tabella che contiene il trigger da eliminare.</span><span class="sxs-lookup"><span data-stu-id="3d72c-130">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to delete.</span></span>  
  
3.  <span data-ttu-id="3d72c-131">Espandere **Trigger**, fare clic con il pulsante destro del mouse sul trigger da eliminare, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3d72c-131">Expand **Triggers**, right-click the trigger to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="3d72c-132">Nella finestra di dialogo **Elimina oggetto** , verificare il trigger da eliminare, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d72c-132">In the **Delete Object** dialog box, verify the trigger to delete, and then click **OK**.</span></span>  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="3d72c-133">Per abilitare e disabilitare un trigger DML</span><span class="sxs-lookup"><span data-stu-id="3d72c-133">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="3d72c-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="3d72c-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3d72c-135">Espandere il database desiderato, espandere **Tabelle**, quindi espandere la tabella che contiene il trigger da disabilitare.</span><span class="sxs-lookup"><span data-stu-id="3d72c-135">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to disable.</span></span>  
  
3.  <span data-ttu-id="3d72c-136">Espandere **Trigger**, fare clic con il pulsante destro del mouse sul trigger da disabilitare, quindi fare clic su **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="3d72c-136">Expand **Triggers**, right-click the trigger to disable, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="3d72c-137">Per abilitare il trigger, fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="3d72c-137">To enable the trigger, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3d72c-138">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3d72c-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="3d72c-139">Per eliminare un trigger DML</span><span class="sxs-lookup"><span data-stu-id="3d72c-139">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="3d72c-140">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d72c-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d72c-141">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3d72c-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3d72c-142">Copiare e incollare gli esempi seguenti nella finestra delle query.</span><span class="sxs-lookup"><span data-stu-id="3d72c-142">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="3d72c-143">Per creare il trigger [, eseguire l'istruzione](/sql/t-sql/statements/create-trigger-transact-sql) CREATE TRIGGER `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="3d72c-143">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="3d72c-144">Per eliminare il trigger, eseguire l'istruzione [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3d72c-144">To delete the trigger, execute the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) statement.</span></span>  
  
```sql  
--Create the trigger.  
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
--Delete the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ('Sales.bonus_reminder', 'TR') IS NOT NULL  
   DROP TRIGGER Sales.bonus_reminder;  
GO  
  
```  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="3d72c-145">Per abilitare e disabilitare un trigger DML</span><span class="sxs-lookup"><span data-stu-id="3d72c-145">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="3d72c-146">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d72c-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d72c-147">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3d72c-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3d72c-148">Copiare e incollare gli esempi seguenti nella finestra delle query.</span><span class="sxs-lookup"><span data-stu-id="3d72c-148">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="3d72c-149">Per creare il trigger [, eseguire l'istruzione](/sql/t-sql/statements/create-trigger-transact-sql) CREATE TRIGGER `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="3d72c-149">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="3d72c-150">Per disabilitare e abilitare il trigger, eseguire le istruzioni [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) e [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="3d72c-150">To disable and enable the trigger, execute the [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) and [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) statements, respectively.</span></span>  
  
```sql  
--Create the trigger.  
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
--Disable the trigger.  
USE AdventureWorks2012;  
GO  
DISABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
  
```  
  
```sql  
--Enable the trigger.  
USE AdventureWorks2012;  
GO  
ENABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d72c-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d72c-151">See Also</span></span>  
 <span data-ttu-id="3d72c-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-158">[Ottieni informazioni sui trigger DML](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="3d72c-158">[Get Information About DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="3d72c-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="3d72c-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3d72c-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="3d72c-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d72c-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
