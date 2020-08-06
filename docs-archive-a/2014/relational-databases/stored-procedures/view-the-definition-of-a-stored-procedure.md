---
title: Visualizzare la definizione di una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], viewing
- definition of stored procedure
- viewing stored procedures
- displaying stored procedures
ms.assetid: 93318587-a0c5-4788-946f-3b5dc8372ea9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4da455d38f984b08ee1f396f26cd4cc85411be92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628584"
---
# <a name="view-the-definition-of-a-stored-procedure"></a><span data-ttu-id="0dfd7-102">Visualizzare la definizione di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="0dfd7-102">View the Definition of a Stored Procedure</span></span>
    
##  <a name="you-can-view-the-definition-of-a-stored-procedure-in-ssmanstudiofull-using-object-explorer-menu-options-or-in-the-query-editor-using-tsql-this-topic-describes-how-to-view-the-definition-of-procedure-in-object-explorer-and-by-using-a-system-stored-procedure-system-function-and-object-catalog-view-in-the-query-editor"></a><a name="Top"></a> <span data-ttu-id="0dfd7-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] è possibile visualizzare la definizione di una stored procedure mediante le opzioni di menu di Esplora oggetti o mediante [!INCLUDE[tsql](../../includes/tsql-md.md)]nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-103">You can view the definition of a stored procedure in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or in the Query Editor using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0dfd7-104">In questo argomento viene descritto come visualizzare la definizione di una stored procedura in Esplora oggetti e nell'editor di query mediante una stored procedure di sistema, una funzione di sistema e una vista del catalogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-104">This topic describes how to view the definition of procedure in Object Explorer and by using a system stored procedure, system function, and object catalog view in the Query Editor.</span></span>  
  
-   <span data-ttu-id="0dfd7-105">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="0dfd7-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="0dfd7-106">**Per visualizzare la definizione di una procedura mediante:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="0dfd7-106">**To view the definition of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0dfd7-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0dfd7-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0dfd7-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0dfd7-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0dfd7-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0dfd7-109">Permissions</span></span>  
 <span data-ttu-id="0dfd7-110">Stored procedure di sistema: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="0dfd7-110">System Stored Procedure: `sp_helptext`</span></span>  
 <span data-ttu-id="0dfd7-111">È richiesta l'appartenenza al ruolo **public** .</span><span class="sxs-lookup"><span data-stu-id="0dfd7-111">Requires membership in the **public** role.</span></span> <span data-ttu-id="0dfd7-112">Le definizioni degli oggetti di sistema sono visibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-112">System object definitions are publicly visible.</span></span> <span data-ttu-id="0dfd7-113">La definizione degli oggetti utente è visibile al proprietario degli oggetti o agli utenti autorizzati che hanno una delle autorizzazioni seguenti: ALTER, CONTROL, TAKE OWNERSHIP o VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-113">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span>  
  
 <span data-ttu-id="0dfd7-114">Funzione di sistema: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="0dfd7-114">System Function: `OBJECT_DEFINITION`</span></span>  
 <span data-ttu-id="0dfd7-115">Le definizioni degli oggetti di sistema sono visibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-115">System object definitions are publicly visible.</span></span> <span data-ttu-id="0dfd7-116">La definizione degli oggetti utente è visibile al proprietario degli oggetti o agli utenti autorizzati che hanno una delle autorizzazioni seguenti: ALTER, CONTROL, TAKE OWNERSHIP o VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-116">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="0dfd7-117">Queste autorizzazioni sono assegnate implicitamente ai membri dei ruoli predefiniti del database **db_owner**, **db_ddladmin**e **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="0dfd7-117">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="0dfd7-118">Vista del catalogo dell'oggetto: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="0dfd7-118">Object Catalog View: `sys.sql_modules`</span></span>  
 <span data-ttu-id="0dfd7-119">La visibilità dei metadati nelle viste del catalogo è limitata alle entità a protezione diretta di cui l'utente è proprietario o per le quali dispone di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-119">The visibility of the metadata in catalog views is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="0dfd7-120">Per altre informazioni, vedere [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0dfd7-120">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="how-to-view-the-definition-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="0dfd7-121">Visualizzazione della definizione di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="0dfd7-121">How to View the Definition of a Stored Procedure</span></span>  
 <span data-ttu-id="0dfd7-122">È possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="0dfd7-122">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="0dfd7-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0dfd7-123">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="0dfd7-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0dfd7-124">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0dfd7-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0dfd7-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="0dfd7-126">**Per visualizzare la definizione di una stored procedure in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="0dfd7-126">**To view the definition a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="0dfd7-127">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0dfd7-128">Espandere **Database**, espandere il database a cui appartiene la stored procedure, quindi espandere **Programmabilità**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="0dfd7-129">Espandere **Stored procedure**, fare clic con il pulsante destro del mouse sulla procedura, scegliere **Crea script per stored procedure**, infine fare clic su una delle opzioni seguenti: **Genera codice per istruzione CREATE in**, **Genera codice per istruzione ALTER in** o **Genera codice per istruzioni DROP e CREATE in**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-129">Expand **Stored Procedures**, right-click the procedure and then click **Script Stored Procedure as**, and then click one of the following: **Create To**, **Alter To**, or **Drop and Create To**.</span></span>  
  
4.  <span data-ttu-id="0dfd7-130">Selezionare **Nuova finestra editor di query**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-130">Select **New Query Editor Window**.</span></span> <span data-ttu-id="0dfd7-131">Verrà visualizzata la definizione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-131">This will display the procedure definition.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0dfd7-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0dfd7-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="0dfd7-133">**Per visualizzare la definizione di una stored procedure nell'editor di query**</span><span class="sxs-lookup"><span data-stu-id="0dfd7-133">**To view the definition of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="0dfd7-134">Stored procedure di sistema: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="0dfd7-134">System Stored Procedure: `sp_helptext`</span></span>  
 1.  <span data-ttu-id="0dfd7-135">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dfd7-135">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0dfd7-136">Sulla barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-136">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0dfd7-137">Nella finestra Query immettere l'istruzione seguente che usano la stored procedure di sistema `sp_helptext`.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-137">In the query window, enter the following statement that uses the `sp_helptext` system stored procedure.</span></span> <span data-ttu-id="0dfd7-138">Modificare il nome del database e della stored procedure in modo da indicare il database e la stored procedure desiderati.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-138">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_helptext N'AdventureWorks2012.dbo.uspLogError';  
    ```  
  
 <span data-ttu-id="0dfd7-139">Funzione di sistema: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="0dfd7-139">System Function: `OBJECT_DEFINITION`</span></span>  
 1.  <span data-ttu-id="0dfd7-140">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dfd7-140">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0dfd7-141">Sulla barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-141">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0dfd7-142">Nella finestra Query immettere le istruzioni seguenti che usano la funzione di sistema `OBJECT_DEFINITION`.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-142">In the query window, enter the following statements that use the `OBJECT_DEFINITION` system function.</span></span> <span data-ttu-id="0dfd7-143">Modificare il nome del database e della stored procedure in modo da indicare il database e la stored procedure desiderati.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-143">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
 <span data-ttu-id="0dfd7-144">Vista del catalogo dell'oggetto: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="0dfd7-144">Object Catalog View: `sys.sql_modules`</span></span>  
 1.  <span data-ttu-id="0dfd7-145">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dfd7-145">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0dfd7-146">Sulla barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-146">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0dfd7-147">Nella finestra Query immettere le istruzioni seguenti che usano la vista del catalogo `sys.sql_modules`.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-147">In the query window, enter the following statements that use the `sys.sql_modules` catalog view.</span></span> <span data-ttu-id="0dfd7-148">Modificare il nome del database e della stored procedure in modo da indicare il database e la stored procedure desiderati.</span><span class="sxs-lookup"><span data-stu-id="0dfd7-148">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition  
    FROM sys.sql_modules  
    WHERE object_id = (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0dfd7-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dfd7-149">See Also</span></span>  
 <span data-ttu-id="0dfd7-150">[Creazione di una stored procedure](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0dfd7-150">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="0dfd7-151">[Modificare una stored procedure](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0dfd7-151">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="0dfd7-152">[Eliminare una stored procedure](delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0dfd7-152">[Delete a Stored Procedure](delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="0dfd7-153">[Rinominare una stored procedure](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0dfd7-153">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="0dfd7-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0dfd7-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span></span>  
 <span data-ttu-id="0dfd7-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0dfd7-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="0dfd7-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0dfd7-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span></span>  
 [<span data-ttu-id="0dfd7-157">OBJECT_ID &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0dfd7-157">OBJECT_ID &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-id-transact-sql)  
  
  
