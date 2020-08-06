---
title: Visualizzare le dipendenze di una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], dependencies
- displaying stored procedure dependencies
- viewing stored procedure dependencies
ms.assetid: 6ae0a369-1bc7-4ae4-be89-2b483697cd1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 790684035d2db3b697fb8b718c96182eda8f1186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638359"
---
# <a name="view-the-dependencies-of-a-stored-procedure"></a><span data-ttu-id="62ac0-102">Visualizzare le dipendenze di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="62ac0-102">View the Dependencies of a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-view-stored-procedure-dependencies-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="62ac0-103">Questo argomento illustra come visualizzare le dipendenze di una stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62ac0-103">This topic describes how to view stored procedure dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="62ac0-104">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="62ac0-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="62ac0-105">**Per visualizzare le dipendenze di una procedura usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="62ac0-105">**To view the dependencies of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62ac0-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="62ac0-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="62ac0-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="62ac0-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="62ac0-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="62ac0-108">Permissions</span></span>  
 <span data-ttu-id="62ac0-109">Funzione di sistema: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="62ac0-109">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="62ac0-110">Richiede l'autorizzazione CONTROL per l'entità a cui si fa riferimento e l'autorizzazione SELECT per sys.dm_sql_referencing_entities.</span><span class="sxs-lookup"><span data-stu-id="62ac0-110">Requires CONTROL permission on the referenced entity and SELECT permission on sys.dm_sql_referencing_entities.</span></span> <span data-ttu-id="62ac0-111">Quando l'entità a cui si fa riferimento è una funzione di partizione, è necessaria l'autorizzazione CONTROL per il database.</span><span class="sxs-lookup"><span data-stu-id="62ac0-111">When the referenced entity is a partition function, CONTROL permission on the database is required.</span></span> <span data-ttu-id="62ac0-112">Per impostazione predefinita, l'autorizzazione SELECT è concessa al ruolo public.</span><span class="sxs-lookup"><span data-stu-id="62ac0-112">By default, SELECT permission is granted to public.</span></span>  
  
 <span data-ttu-id="62ac0-113">Funzione di sistema: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="62ac0-113">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="62ac0-114">È richiesta l'autorizzazione SELECT per sys.dm_sql_referenced_entities e l'autorizzazione VIEW DEFINITION per l'entità di riferimento.</span><span class="sxs-lookup"><span data-stu-id="62ac0-114">Requires SELECT permission on sys.dm_sql_referenced_entities and VIEW DEFINITION permission on the referencing entity.</span></span> <span data-ttu-id="62ac0-115">Per impostazione predefinita, l'autorizzazione SELECT è concessa al ruolo public.</span><span class="sxs-lookup"><span data-stu-id="62ac0-115">By default, SELECT permission is granted to public.</span></span> <span data-ttu-id="62ac0-116">È richiesta l'autorizzazione VIEW DEFINITION per il database o un'autorizzazione ALTER ANY DATABASE DDL TRIGGER per il database corrente quando l'entità di riferimento è un trigger DDL a livello di database.</span><span class="sxs-lookup"><span data-stu-id="62ac0-116">Requires VIEW DEFINITION permission on the database or ALTER DATABASE DDL TRIGGER permission on the database when the referencing entity is a database-level DDL trigger.</span></span> <span data-ttu-id="62ac0-117">È richiesta l'autorizzazione VIEW ANY DEFINITION per il server quando l'entità di riferimento è un trigger DDL a livello di server.</span><span class="sxs-lookup"><span data-stu-id="62ac0-117">Requires VIEW ANY DEFINITION permission on the server when the referencing entity is a server-level DDL trigger.</span></span>  
  
 <span data-ttu-id="62ac0-118">Vista del catalogo dell'oggetto: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="62ac0-118">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="62ac0-119">Sono richieste l'autorizzazione VIEW DEFINITION sul database e l'autorizzazione SELECT su sys.sql_expression_dependencies per il database.</span><span class="sxs-lookup"><span data-stu-id="62ac0-119">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="62ac0-120">L'autorizzazione SELECT è concessa per impostazione predefinita solo ai membri del ruolo predefinito del database di db_owner.</span><span class="sxs-lookup"><span data-stu-id="62ac0-120">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="62ac0-121">Quando le autorizzazioni SELECT e VIEW DEFINITION vengono concesse a un altro utente, l'utente autorizzato può visualizzare tutte le dipendenze nel database.</span><span class="sxs-lookup"><span data-stu-id="62ac0-121">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="how-to-view-the-dependencies-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="62ac0-122">Modalità di visualizzazione delle dipendenze di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="62ac0-122">How to View the Dependencies of a Stored Procedure</span></span>  
 <span data-ttu-id="62ac0-123">È possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="62ac0-123">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="62ac0-124">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="62ac0-124">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="62ac0-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62ac0-125">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="62ac0-126">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="62ac0-126">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="62ac0-127">**Per visualizzare le dipendenze di una stored procedure in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="62ac0-127">**To view the dependencies of a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="62ac0-128">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="62ac0-128">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="62ac0-129">Espandere **Database**, espandere il database a cui appartiene la stored procedure, quindi espandere **Programmabilità**.</span><span class="sxs-lookup"><span data-stu-id="62ac0-129">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="62ac0-130">Espandere **Stored procedure**, fare clic con il pulsante destro del mouse sulla stored procedure, quindi scegliere **Visualizza dipendenze**.</span><span class="sxs-lookup"><span data-stu-id="62ac0-130">Expand **Stored Procedures**, right-click the procedure and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="62ac0-131">Visualizzare l'elenco di oggetti che dipendono dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-131">View the list of objects that depend on the procedure.</span></span>  
  
5.  <span data-ttu-id="62ac0-132">Visualizzare l'elenco di oggetti da cui dipende la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-132">View the list of objects on which the procedure depends.</span></span>  
  
6.  <span data-ttu-id="62ac0-133">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="62ac0-133">Click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="62ac0-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62ac0-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="62ac0-135">**Per visualizzare le dipendenze di una stored procedure nell'editor di query**</span><span class="sxs-lookup"><span data-stu-id="62ac0-135">**To view the dependencies of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="62ac0-136">Funzione di sistema: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="62ac0-136">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="62ac0-137">Questa funzione viene usata per visualizzare gli oggetti che dipendono da una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-137">This function is used to display the objects that depend on a procedure.</span></span>  
  
1.  <span data-ttu-id="62ac0-138">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="62ac0-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="62ac0-139">Espandere **Database**ed espandere il database a cui appartiene la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-139">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="62ac0-140">Scegliere **Nuova query** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="62ac0-140">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="62ac0-141">Copiare e incollare gli esempi seguenti nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="62ac0-141">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="62ac0-142">Nel primo esempio viene creata la stored procedure `uspVendorAllInfo` mediante la quale vengono restituiti i nomi di tutti i fornitori nel database [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , i prodotti da essi forniti, nonché le informazioni relative alla posizione creditizia e alla disponibilità.</span><span class="sxs-lookup"><span data-stu-id="62ac0-142">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="62ac0-143">Dopo aver creato la stored procedure, nel secondo esempio viene usata la funzione sys.dm_sql_referencing_entities per visualizzare gli oggetti che dipendono dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-143">After the procedure is created, the second example uses the sys.dm_sql_referencing_entities function to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referencing_schema_name, referencing_entity_name, referencing_id, referencing_class_desc, is_caller_dependent  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');   
    GO  
  
    ```  
  
 <span data-ttu-id="62ac0-144">Funzione di sistema: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="62ac0-144">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="62ac0-145">Questa funzione viene usata per visualizzare gli oggetti da cui dipende una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-145">This function is used to display the objects a procedure depends on.</span></span>  
  
1.  <span data-ttu-id="62ac0-146">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="62ac0-146">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="62ac0-147">Espandere **Database**ed espandere il database a cui appartiene la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-147">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="62ac0-148">Scegliere **Nuova query** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="62ac0-148">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="62ac0-149">Copiare e incollare gli esempi seguenti nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="62ac0-149">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="62ac0-150">Nel primo esempio viene creata la stored procedure `uspVendorAllInfo` mediante la quale vengono restituiti i nomi di tutti i fornitori nel database [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , i prodotti da essi forniti, nonché le informazioni relative alla posizione creditizia e alla disponibilità.</span><span class="sxs-lookup"><span data-stu-id="62ac0-150">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="62ac0-151">Dopo aver creato la stored procedure, nel secondo esempio viene usata la funzione sys.dm_sql_referenced_entities per visualizzare gli oggetti da cui dipende la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-151">After the procedure is created, the second example uses the sys.dm_sql_referenced_entities function to display the objects that the procedure depends on.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referenced_schema_name, referenced_entity_name,  
    referenced_minor_name,referenced_minor_id, referenced_class_desc,  
    is_caller_dependent, is_ambiguous  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');  
    GO  
    ```  
  
 <span data-ttu-id="62ac0-152">Vista del catalogo dell'oggetto: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="62ac0-152">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="62ac0-153">Questa vista può essere usata per visualizzare gli oggetti da cui dipende una stored procedure o che dipendono da una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-153">This view can be used to display objects that a procedure depends on or that depend on a procedure.</span></span>  
  
 <span data-ttu-id="62ac0-154">Visualizzazione degli oggetti che dipendono da una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-154">Displaying the objects that depend on a procedure.</span></span>  
 1.  <span data-ttu-id="62ac0-155">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="62ac0-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="62ac0-156">Espandere **Database**ed espandere il database a cui appartiene la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-156">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="62ac0-157">Scegliere **Nuova query** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="62ac0-157">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="62ac0-158">Copiare e incollare gli esempi seguenti nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="62ac0-158">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="62ac0-159">Nel primo esempio viene creata la stored procedure `uspVendorAllInfo` mediante la quale vengono restituiti i nomi di tutti i fornitori nel database [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , i prodotti da essi forniti, nonché le informazioni relative alla posizione creditizia e alla disponibilità.</span><span class="sxs-lookup"><span data-stu-id="62ac0-159">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="62ac0-160">Al termine della creazione della stored procedure, nel secondo esempio viene usata la vista sys.sql_expression_dependencies per visualizzare gli oggetti che dipendono dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-160">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_SCHEMA_NAME ( referencing_id ) AS referencing_schema_name,  
        OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referenced_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
 <span data-ttu-id="62ac0-161">Visualizzazione degli oggetti da cui dipende una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-161">Displaying the objects a procedure depends on.</span></span>  
 1.  <span data-ttu-id="62ac0-162">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="62ac0-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="62ac0-163">Espandere **Database**ed espandere il database a cui appartiene la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-163">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="62ac0-164">Scegliere **Nuova query** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="62ac0-164">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="62ac0-165">Copiare e incollare gli esempi seguenti nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="62ac0-165">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="62ac0-166">Nel primo esempio viene creata la stored procedure `uspVendorAllInfo` mediante la quale vengono restituiti i nomi di tutti i fornitori nel database [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , i prodotti da essi forniti, nonché le informazioni relative alla posizione creditizia e alla disponibilità.</span><span class="sxs-lookup"><span data-stu-id="62ac0-166">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="62ac0-167">Al termine della creazione della stored procedure, nel secondo esempio viene usata la vista sys.sql_expression_dependencies per visualizzare gli oggetti da cui dipende la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62ac0-167">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects the procedure depends on.</span></span>  
  
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
    WHERE referencing_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="62ac0-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62ac0-168">See Also</span></span>  
 <span data-ttu-id="62ac0-169">[Rinominare una stored procedure](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="62ac0-169">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="62ac0-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62ac0-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span></span>  
 <span data-ttu-id="62ac0-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62ac0-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span></span>  
 [<span data-ttu-id="62ac0-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="62ac0-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
  
