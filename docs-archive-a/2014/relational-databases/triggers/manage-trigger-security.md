---
title: Gestire la sicurezza dei trigger | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], security
ms.assetid: e94720a8-a3a2-4364-b0a3-bbe86e3ce4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: fdc176dcad50c3bf28f058c3724a01267975bfc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637128"
---
# <a name="manage-trigger-security"></a><span data-ttu-id="5e908-102">Gestione della sicurezza dei trigger</span><span class="sxs-lookup"><span data-stu-id="5e908-102">Manage Trigger Security</span></span>
  <span data-ttu-id="5e908-103">Per impostazione predefinita, i trigger DML e DDL vengono eseguiti nel contesto dell'utente che li chiama.</span><span class="sxs-lookup"><span data-stu-id="5e908-103">By default, both DML and DDL triggers execute under the context of the user that calls the trigger.</span></span> <span data-ttu-id="5e908-104">Il chiamante di un trigger è l'utente che esegue l'istruzione che causa l'esecuzione del trigger.</span><span class="sxs-lookup"><span data-stu-id="5e908-104">The caller of a trigger is the user that executes the statement that causes the trigger to run.</span></span> <span data-ttu-id="5e908-105">Se ad esempio l'utente **Mary** esegue un'istruzione DELETE che causa l'esecuzione del trigger DML **DML_trigMary** , il codice all'interno di **DML_trigMary** viene eseguito nel contesto dei privilegi utente relativi a **Mary**.</span><span class="sxs-lookup"><span data-stu-id="5e908-105">For example, if user **Mary** executes a DELETE statement that causes DML trigger **DML_trigMary** to run, the code inside **DML_trigMary** executes in the context of the user privileges for **Mary**.</span></span> <span data-ttu-id="5e908-106">Il funzionamento predefinito può essere sfruttato dagli utenti che desiderano introdurre malware nel database o nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="5e908-106">This default behavior can be exploited by users who want to introduce malicious code in the database or server instance.</span></span> <span data-ttu-id="5e908-107">Ad esempio, il trigger DDL seguente viene creato dall'utente `JohnDoe`:</span><span class="sxs-lookup"><span data-stu-id="5e908-107">For example, the following DDL trigger is created by user `JohnDoe`:</span></span>  
  
 `CREATE TRIGGER DDL_trigJohnDoe`  
  
 `ON DATABASE`  
  
 `FOR ALTER_TABLE`  
  
 `AS`  
  
 `GRANT CONTROL SERVER TO JohnDoe ;`  
  
 `GO`  
  
 <span data-ttu-id="5e908-108">Il trigger indica che non appena un utente che dispone dell'autorizzazione per l'esecuzione di un'istruzione `GRANT CONTROL SERVER` , ad esempio un membro del ruolo predefinito del server **sysadmin** , esegue un'istruzione `ALTER TABLE` , all'utente `JohnDoe` viene concessa l'autorizzazione `CONTROL SERVER` .</span><span class="sxs-lookup"><span data-stu-id="5e908-108">What this trigger means is that as soon as a user that has permission to execute a `GRANT CONTROL SERVER` statement, such as a member of the **sysadmin** fixed server role, executes an `ALTER TABLE` statement, `JohnDoe` is granted `CONTROL SERVER` permission.</span></span> <span data-ttu-id="5e908-109">In altre parole, anche se `JohnDoe` non può concedere l'autorizzazione `CONTROL SERVER` a se stesso, ha abilitato il codice del trigger che gli concede tale autorizzazione per l'esecuzione con privilegi con escalation.</span><span class="sxs-lookup"><span data-stu-id="5e908-109">In other words, although `JohnDoe` cannot grant `CONTROL SERVER` permission to himself, he enabled the trigger code that grants him this permission to execute under escalated privileges.</span></span> <span data-ttu-id="5e908-110">I trigger DML e DDL sono esposti a questo tipo di minaccia per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5e908-110">Both DML and DDL triggers are open to this kind of security threat.</span></span>  
  
## <a name="trigger-security-best-practices"></a><span data-ttu-id="5e908-111">Procedure consigliate per la sicurezza dei trigger</span><span class="sxs-lookup"><span data-stu-id="5e908-111">Trigger Security Best Practices</span></span>  
 <span data-ttu-id="5e908-112">Per impedire l'esecuzione del codice del trigger con privilegi alzati di livello, è possibile adottare le misure seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e908-112">You can take the following measures to prevent trigger code from executing under escalated privileges:</span></span>  
  
-   <span data-ttu-id="5e908-113">Individuare i trigger DML e DDL esistenti nel database e nell'istanza del server eseguendo query sulle viste del catalogo [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) e [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5e908-113">Be aware of the DML and DDL triggers that exist in the database and on the server instance by querying the [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) and [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) catalog views.</span></span> <span data-ttu-id="5e908-114">La query seguente restituisce tutti i trigger DML e DDL a livello di database nel database corrente e tutti i trigger DDL a livello di server nell'istanza del server:</span><span class="sxs-lookup"><span data-stu-id="5e908-114">The following query returns all DML and database-level DDL triggers in the current database, and all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    SELECT type, name, parent_class_desc FROM sys.triggers  
    UNION  
    SELECT type, name, parent_class_desc FROM sys.server_triggers ;  
    ```  
  
-   <span data-ttu-id="5e908-115">Per disabilitare i trigger che possono compromettere l'integrità del database o del server se vengono eseguiti con privilegi alzati di livello, usare [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5e908-115">Use [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) to disable triggers that can harm the integrity of the database or server if the triggers execute under escalated privileges.</span></span> <span data-ttu-id="5e908-116">L'istruzione seguente disabilita tutti i trigger DDL a livello di database nel database corrente:</span><span class="sxs-lookup"><span data-stu-id="5e908-116">The following statement disables all database-level DDL triggers in the current database:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON DATABASE  
    ```  
  
     <span data-ttu-id="5e908-117">L'istruzione seguente disabilita tutti i trigger DDL a livello di server nell'istanza del server:</span><span class="sxs-lookup"><span data-stu-id="5e908-117">This statement disables all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON ALL SERVER  
    ```  
  
     <span data-ttu-id="5e908-118">L'istruzione seguente disabilita tutti i trigger DML nel database corrente:</span><span class="sxs-lookup"><span data-stu-id="5e908-118">This statement disables all DML triggers in the current database:</span></span>  
  
    ```  
    DECLARE @schema_name sysname, @trigger_name sysname, @object_name sysname ;  
    DECLARE @sql nvarchar(max) ;  
    DECLARE trig_cur CURSOR FORWARD_ONLY READ_ONLY FOR  
        SELECT SCHEMA_NAME(schema_id) AS schema_name,  
            name AS trigger_name,  
            OBJECT_NAME(parent_object_id) as object_name  
        FROM sys.objects WHERE type in ('TR', 'TA') ;  
  
    OPEN trig_cur ;  
    FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        SELECT @sql = 'DISABLE TRIGGER ' + QUOTENAME(@schema_name) + '.'  
            + QUOTENAME(@trigger_name) +  
            ' ON ' + QUOTENAME(@schema_name) + '.'   
            + QUOTENAME(@object_name) + ' ; ' ;  
        EXEC (@sql) ;  
        FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
    END  
    GO  
  
    -- Verify triggers are disabled. Should return an empty result set.  
    SELECT * FROM sys.triggers WHERE is_disabled = 0 ;  
    GO  
  
    CLOSE trig_cur ;  
    DEALLOCATE trig_cur;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5e908-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e908-119">See Also</span></span>  
 <span data-ttu-id="5e908-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e908-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="5e908-121">[Trigger DML](../triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="5e908-121">[DML Triggers](../triggers/dml-triggers.md) </span></span>  
 [<span data-ttu-id="5e908-122">Trigger DDL</span><span class="sxs-lookup"><span data-stu-id="5e908-122">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
