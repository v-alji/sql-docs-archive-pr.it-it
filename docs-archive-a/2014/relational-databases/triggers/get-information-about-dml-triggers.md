---
title: Recuperare informazioni sui trigger DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- viewing DML triggers
- DML triggers, metadata
- displaying DML triggers
- status information [SQL Server], triggers
- DML triggers, viewing
ms.assetid: 37574aac-181d-4aca-a2cc-8abff64237dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2f65976d2f517137e23bd9e5e1c98cc76324bc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637140"
---
# <a name="get-information-about-dml-triggers"></a><span data-ttu-id="ed242-102">Ottieni informazioni sui trigger DML</span><span class="sxs-lookup"><span data-stu-id="ed242-102">Get Information About DML Triggers</span></span>
  <span data-ttu-id="ed242-103">In questo argomento viene descritto come ottenere informazioni sui trigger DML in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed242-103">This topic describes how to get information about DML triggers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ed242-104">Queste informazioni possono includere i tipi di trigger in una tabella, nonché il nome, il proprietario e la data di creazione o modifica di un trigger.</span><span class="sxs-lookup"><span data-stu-id="ed242-104">This information can include the types of triggers on a table, the name of a trigger, its owner and the date it was created or modified.</span></span> <span data-ttu-id="ed242-105">Se il trigger non è stato crittografato al momento della creazione, se ne ottiene la definizione.</span><span class="sxs-lookup"><span data-stu-id="ed242-105">If the trigger was not encrypted when it was created, you obtain the definition of the trigger.</span></span> <span data-ttu-id="ed242-106">È possibile utilizzare la definizione per comprendere gli effetti del trigger sulla tabella su cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="ed242-106">You can use the definition to help you understand how a trigger affects the table up on which it is defined.</span></span> <span data-ttu-id="ed242-107">È inoltre possibile rilevare gli oggetti utilizzati da un trigger specifico.</span><span class="sxs-lookup"><span data-stu-id="ed242-107">Also, you can find out the objects that a specific trigger uses.</span></span> <span data-ttu-id="ed242-108">Con queste informazioni, è possibile identificare gli oggetti che influiscono sul trigger qualora vengano modificati o eliminati dal database.</span><span class="sxs-lookup"><span data-stu-id="ed242-108">With this information, you can identify the objects that affect the trigger if they are changed or deleted in the database.</span></span>  
  
 <span data-ttu-id="ed242-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ed242-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ed242-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ed242-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ed242-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ed242-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ed242-112">**Per ottenere informazioni sui trigger DML utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="ed242-112">**To get information about DML triggers, using:**</span></span>  
  
     [<span data-ttu-id="ed242-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed242-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ed242-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed242-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ed242-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ed242-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ed242-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ed242-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ed242-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ed242-117">Permissions</span></span>  
 <span data-ttu-id="ed242-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span><span class="sxs-lookup"><span data-stu-id="ed242-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="ed242-119">Per altre informazioni, vedere [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ed242-119">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
 <span data-ttu-id="ed242-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span><span class="sxs-lookup"><span data-stu-id="ed242-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span></span>  
 <span data-ttu-id="ed242-121">È richiesta l'appartenenza al ruolo **public** .</span><span class="sxs-lookup"><span data-stu-id="ed242-121">Requires membership in the **public** role.</span></span> <span data-ttu-id="ed242-122">La definizione degli oggetti utente è visibile al proprietario degli oggetti o agli utenti autorizzati che hanno una delle autorizzazioni seguenti: ALTER, CONTROL, TAKE OWNERSHIP o VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="ed242-122">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="ed242-123">Queste autorizzazioni sono assegnate implicitamente ai membri dei ruoli predefiniti del database **db_owner**, **db_ddladmin**e **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="ed242-123">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="ed242-124">**sys.sql_expression_dependencies**</span><span class="sxs-lookup"><span data-stu-id="ed242-124">**sys.sql_expression_dependencies**</span></span>  
 <span data-ttu-id="ed242-125">Sono richieste l'autorizzazione VIEW DEFINITION sul database e l'autorizzazione SELECT su **sys.sql_expression_dependencies** per il database.</span><span class="sxs-lookup"><span data-stu-id="ed242-125">Requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="ed242-126">L'autorizzazione SELECT è concessa per impostazione predefinita solo ai membri del ruolo predefinito del database **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="ed242-126">By default, SELECT permission is granted only to members of the **db_owner** fixed database role.</span></span> <span data-ttu-id="ed242-127">Quando le autorizzazioni SELECT e VIEW DEFINITION vengono concesse a un altro utente, l'utente autorizzato può visualizzare tutte le dipendenze nel database.</span><span class="sxs-lookup"><span data-stu-id="ed242-127">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ed242-128">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed242-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="ed242-129">Per visualizzare la definizione di un trigger DML</span><span class="sxs-lookup"><span data-stu-id="ed242-129">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="ed242-130">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="ed242-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ed242-131">Espandere il database desiderato, espandere **Tabelle**, quindi espandere la tabella che contiene il trigger di cui si desidera visualizzare la definizione.</span><span class="sxs-lookup"><span data-stu-id="ed242-131">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger for which you want to view the definition.</span></span>  
  
3.  <span data-ttu-id="ed242-132">Espandere **Trigger**, fare clic con il pulsante destro del mouse sul trigger desiderato, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ed242-132">Expand **Triggers**, right-click the trigger you want, and then click **Modify**.</span></span> <span data-ttu-id="ed242-133">La definizione del trigger DML viene visualizzata nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="ed242-133">The definition of the DML trigger appears in the query window.</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="ed242-134">Per visualizzare le dipendenze di un trigger DML</span><span class="sxs-lookup"><span data-stu-id="ed242-134">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="ed242-135">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="ed242-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ed242-136">Espandere il database desiderato, espandere **Tabelle**, quindi espandere la tabella che contiene il trigger e le relative dipendenze che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="ed242-136">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger and its dependencies that you want to view.</span></span>  
  
3.  <span data-ttu-id="ed242-137">Espandere **Trigger**, fare clic con il pulsante destro del mouse sul trigger desiderato, quindi scegliere **Visualizza dipendenze**.</span><span class="sxs-lookup"><span data-stu-id="ed242-137">Expand **Triggers**, right-click the trigger you want, and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="ed242-138">Nella finestra di dialogo **Dipendenze oggetto** selezionare **Oggetti che dipendono da \<DML trigger name>** per visualizzare gli oggetti che dipendono dal trigger DML.</span><span class="sxs-lookup"><span data-stu-id="ed242-138">In the **Object Dependencies** window, to view the objects that depend on the DML trigger, select **Objects that depend on \<DML trigger name>**.</span></span> <span data-ttu-id="ed242-139">Gli oggetti vengono visualizzati nell'area **Dipendenze** .</span><span class="sxs-lookup"><span data-stu-id="ed242-139">The objects appear in the **Dependencies** area.</span></span>  
  
     <span data-ttu-id="ed242-140">Per visualizzare gli oggetti da cui dipende il trigger DML, selezionare **Oggetti da cui dipende \<DML trigger name>** .</span><span class="sxs-lookup"><span data-stu-id="ed242-140">To view the objects on which the DML depends, select **Objects on which \<DML trigger name> depends**.</span></span> <span data-ttu-id="ed242-141">Gli oggetti vengono visualizzati nell'area **Dipendenze** .</span><span class="sxs-lookup"><span data-stu-id="ed242-141">The objects appear in the **Dependencies** area.</span></span> <span data-ttu-id="ed242-142">Espandere ogni nodo per visualizzare tutti gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="ed242-142">Expand each node to see all the objects.</span></span>  
  
5.  <span data-ttu-id="ed242-143">Per ottenere informazioni su un oggetto visualizzato nell'area **Dipendenze** , fare clic sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ed242-143">To obtain information about an object that appears in the **Dependencies** area, click the object.</span></span> <span data-ttu-id="ed242-144">Nel campo **Oggetto selezionato** le informazioni vengono fornite nelle caselle **Nome**, **Tipo**e **Tipo dipendenza** .</span><span class="sxs-lookup"><span data-stu-id="ed242-144">In the **Selected object** field, information is provided in the **Name**, **Type**, and **Dependency type** boxes.</span></span>  
  
6.  <span data-ttu-id="ed242-145">Per chiudere la finestra **Dipendenze oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed242-145">To close the **Object Dependencies** window, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ed242-146">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed242-146">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="ed242-147">Per visualizzare la definizione di un trigger DML</span><span class="sxs-lookup"><span data-stu-id="ed242-147">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="ed242-148">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed242-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed242-149">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ed242-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ed242-150">Copiare e incollare uno degli esempi seguenti nella finestra della query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ed242-150">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="ed242-151">In ogni esempio viene illustrato come visualizzare la definizione del trigger `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="ed242-151">Each example shows how you can view the definition of the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT definition   
FROM sys.sql_modules  
WHERE object_id = OBJECT_ID(N'Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_DEFINITION (OBJECT_ID(N'Person.iuPerson')) AS ObjectDefinition;   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
EXEC sp_helptext 'Person.iuPerson'  
GO  
  
```  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="ed242-152">Per visualizzare le dipendenze di un trigger DML</span><span class="sxs-lookup"><span data-stu-id="ed242-152">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="ed242-153">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed242-153">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed242-154">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ed242-154">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ed242-155">Copiare e incollare uno degli esempi seguenti nella finestra della query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ed242-155">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="ed242-156">In ogni esempio viene illustrato come visualizzare le dipendenze del trigger `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="ed242-156">Each example shows how you can view the dependencies of `iuPerson` trigger.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
    o.type_desc AS referencing_desciption,   
    COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
    referencing_class_desc, referenced_class_desc,   
    referenced_server_name, referenced_database_name, referenced_schema_name,   
    referenced_entity_name,   
    COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,   
    is_caller_dependent, is_ambiguous  
FROM sys.sql_expression_dependencies AS sed  
INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
WHERE referencing_id = OBJECT_ID(N'Person.iuPerson');   
GO  
  
```  
  
#### <a name="to-view-information-about-dml-triggers-in-the-database"></a><span data-ttu-id="ed242-157">Per visualizzare informazioni sui trigger DML nel database</span><span class="sxs-lookup"><span data-stu-id="ed242-157">To view information about DML triggers in the database</span></span>  
  
1.  <span data-ttu-id="ed242-158">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed242-158">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed242-159">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ed242-159">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ed242-160">Copiare e incollare uno degli esempi seguenti nella finestra della query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ed242-160">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="ed242-161">In ogni esempio viene illustrato come visualizzare informazioni sui trigger DML (`TR`) nel database.</span><span class="sxs-lookup"><span data-stu-id="ed242-161">Each example shows how you can view information about DML triggers (`TR`) in the database.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT  name, parent_id, create_date, modify_date, is_instead_of_trigger  
FROM sys.triggers  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT  name, object_id, schema_id, parent_object_id, type_desc, create_date, modify_date, is_published  
FROM sys.objects  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECTPROPERTY(OBJECT_ID(N'Person.iuPerson'), 'ExecIsInsteadOfTrigger');   
GO  
  
```  
  
#### <a name="to-view-information-about-events-that-fire-a-dml-trigger"></a><span data-ttu-id="ed242-162">Per visualizzare informazioni sugli eventi che attivano un trigger DML</span><span class="sxs-lookup"><span data-stu-id="ed242-162">To view information about events that fire a DML trigger</span></span>  
  
1.  <span data-ttu-id="ed242-163">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed242-163">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed242-164">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ed242-164">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ed242-165">Copiare e incollare uno degli esempi seguenti nella finestra della query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ed242-165">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="ed242-166">In ogni esempio viene illustrato come visualizzare gli eventi che attivano il trigger `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="ed242-166">Each example shows how you can view the events that fire the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT object_id, type, type_desc, is_trigger_event, event_group_type, event_group_type_desc   
FROM sys.events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO   
SELECT object_id, type,is_first, is_last  
FROM sys.trigger_events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed242-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed242-167">See Also</span></span>  
 <span data-ttu-id="ed242-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="ed242-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="ed242-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="ed242-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="ed242-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="ed242-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="ed242-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="ed242-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="ed242-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="ed242-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="ed242-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="ed242-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="ed242-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="ed242-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="ed242-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="ed242-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="ed242-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="ed242-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed242-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="ed242-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed242-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
  
