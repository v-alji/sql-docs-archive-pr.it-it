---
title: Creare una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- new stored procedures
- stored procedures [SQL Server], creating
- creating stored procedures
ms.assetid: 76e8a6ba-1381-4620-b356-4311e1331ca7
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6781840e6a6c84773f40a6cd0557ccb79b676eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636610"
---
# <a name="create-a-stored-procedure"></a><span data-ttu-id="06ce9-102">Creazione di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="06ce9-102">Create a Stored Procedure</span></span>
  <span data-ttu-id="06ce9-103">In questo argomento viene descritta la procedura per la creazione di una stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="06ce9-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE statement.</span></span>  
  
##  <a name="Top"></a>   
-   <span data-ttu-id="06ce9-104">**Prima di iniziare:**  [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="06ce9-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="06ce9-105">**Per creare una stored procedure, usare:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="06ce9-105">**To create a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="06ce9-106">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="06ce9-106">Permissions</span></span>  
 <span data-ttu-id="06ce9-107">È necessario disporre dell'autorizzazione CREATE PROCEDURE per il database e dell'autorizzazione ALTER per lo schema in cui la stored procedure viene creata.</span><span class="sxs-lookup"><span data-stu-id="06ce9-107">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
##  <a name="how-to-create-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="06ce9-108">Procedura: creazione di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="06ce9-108">How to Create a Stored Procedure</span></span>  
 <span data-ttu-id="06ce9-109">È possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="06ce9-109">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="06ce9-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06ce9-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="06ce9-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06ce9-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="06ce9-112">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06ce9-112">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="06ce9-113">**Per creare una stored procedure in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="06ce9-113">**To create a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="06ce9-114">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="06ce9-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="06ce9-115">Espandere **Database**, il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e quindi **Programmabilità**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="06ce9-116">Fare clic con il pulsante destro del mouse su **Stored procedure**e quindi scegliere **Nuova stored procedure**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-116">Right-click **Stored Procedures**, and then click **New Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="06ce9-117">Scegliere **Imposta valori per parametri modello** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="06ce9-118">Nella finestra di dialogo **Imposta valori per parametri modello** immettere i seguenti valori per i parametri indicati.</span><span class="sxs-lookup"><span data-stu-id="06ce9-118">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="06ce9-119">Parametro</span><span class="sxs-lookup"><span data-stu-id="06ce9-119">Parameter</span></span>|<span data-ttu-id="06ce9-120">Valore</span><span class="sxs-lookup"><span data-stu-id="06ce9-120">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="06ce9-121">Autore</span><span class="sxs-lookup"><span data-stu-id="06ce9-121">Author</span></span>|<span data-ttu-id="06ce9-122">*Nome dell'utente*</span><span class="sxs-lookup"><span data-stu-id="06ce9-122">*Your name*</span></span>|  
    |<span data-ttu-id="06ce9-123">Data di creazione</span><span class="sxs-lookup"><span data-stu-id="06ce9-123">Create Date</span></span>|<span data-ttu-id="06ce9-124">*Data corrente*</span><span class="sxs-lookup"><span data-stu-id="06ce9-124">*Today's date*</span></span>|  
    |<span data-ttu-id="06ce9-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06ce9-125">Description</span></span>|<span data-ttu-id="06ce9-126">Restituisce i dati dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="06ce9-126">Returns employee data.</span></span>|  
    |<span data-ttu-id="06ce9-127">Procedure_name</span><span class="sxs-lookup"><span data-stu-id="06ce9-127">Procedure_name</span></span>|<span data-ttu-id="06ce9-128">HumanResources.uspGetEmployeesTest</span><span class="sxs-lookup"><span data-stu-id="06ce9-128">HumanResources.uspGetEmployeesTest</span></span>|  
    |@Param1|@LastName|  
    |@Datatype_For_Param1|<span data-ttu-id="06ce9-129">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="06ce9-129">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="06ce9-130">Default_Value_For_Param1</span><span class="sxs-lookup"><span data-stu-id="06ce9-130">Default_Value_For_Param1</span></span>|<span data-ttu-id="06ce9-131">NULL</span><span class="sxs-lookup"><span data-stu-id="06ce9-131">NULL</span></span>|  
    |@Param2|@FirstName|  
    |@Datatype_For_Param2|<span data-ttu-id="06ce9-132">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="06ce9-132">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="06ce9-133">Default_Value_For_Param2</span><span class="sxs-lookup"><span data-stu-id="06ce9-133">Default_Value_For_Param2</span></span>|<span data-ttu-id="06ce9-134">NULL</span><span class="sxs-lookup"><span data-stu-id="06ce9-134">NULL</span></span>|  
  
6.  <span data-ttu-id="06ce9-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-135">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="06ce9-136">Nell' **editor di query**sostituire l'istruzione SELECT con l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="06ce9-136">In the **Query Editor**, replace the SELECT statement with the following statement:</span></span>  
  
    ```sql  
    SELECT FirstName, LastName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory  
    WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    ```  
  
8.  <span data-ttu-id="06ce9-137">Per controllare la sintassi, scegliere **Analizza** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-137">To test the syntax, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="06ce9-138">Se viene restituito un messaggio di errore, confrontare le istruzioni con le informazioni precedenti e apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="06ce9-138">If an error message is returned, compare the statements with the information above and correct as needed.</span></span>  
  
9. <span data-ttu-id="06ce9-139">Per creare la stored procedure, nel menu **Query** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-139">To create the procedure, from  the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="06ce9-140">La stored procedure viene creata come un oggetto nel database.</span><span class="sxs-lookup"><span data-stu-id="06ce9-140">The procedure is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="06ce9-141">Per visualizzare la stored procedure nell'elenco di Esplora oggetti, fare clic con il pulsante destro del mouse su **Stored procedure** e scegliere **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-141">To see the procedure listed in Object Explorer, right-click **Stored Procedures** and select **Refresh**.</span></span>  
  
11. <span data-ttu-id="06ce9-142">Per eseguire la stored procedure in Esplora oggetti, fare clic con il pulsante destro del mouse sul nome della stored procedure **HumanResources.uspGetEmployeesTest** e scegliere **Esegui stored procedure**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-142">To run the procedure, in Object Explorer, right-click the stored procedure name **HumanResources.uspGetEmployeesTest** and select **Execute Stored Procedure**.</span></span>  
  
12. <span data-ttu-id="06ce9-143">Nella finestra **Esegui procedura** immettere Margheim come valore per il parametro @LastName e Diane come valore per il parametro @FirstName.</span><span class="sxs-lookup"><span data-stu-id="06ce9-143">In the **Execute Procedure** window, enter Margheim as the value for the parameter @LastName and enter the value Diane as the value for the parameter @FirstName.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="06ce9-144">Convalidare sempre input di tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="06ce9-144">Validate all user input.</span></span> <span data-ttu-id="06ce9-145">Non concatenare l'input dell'utente prima di averlo convalidato.</span><span class="sxs-lookup"><span data-stu-id="06ce9-145">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="06ce9-146">Non eseguire mai un comando creato dall'input dell'utente non convalidato.</span><span class="sxs-lookup"><span data-stu-id="06ce9-146">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="06ce9-147">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06ce9-147">Using Transact-SQL</span></span>  
 <span data-ttu-id="06ce9-148">**Per creare una stored procedure nell'editor di query**</span><span class="sxs-lookup"><span data-stu-id="06ce9-148">**To create a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="06ce9-149">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06ce9-149">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06ce9-150">Nel menu **File** , fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-150">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06ce9-151">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="06ce9-152">In questo esempio viene creata la stessa stored procedure precedente utilizzando un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="06ce9-152">This example creates the same stored procedure as above using a different procedure name.</span></span>  
  
    ```sql
    USE AdventureWorks2012;  
    GO  
    CREATE PROCEDURE HumanResources.uspGetEmployeesTest2   
        @LastName nvarchar(50),   
        @FirstName nvarchar(50)   
    AS
  
        SET NOCOUNT ON;  
        SELECT FirstName, LastName, Department  
        FROM HumanResources.vEmployeeDepartmentHistory  
        WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    GO
    ```  
  
4.  <span data-ttu-id="06ce9-153">Per eseguire la stored procedure, copiare l'esempio seguente e incollarlo in una nuova finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="06ce9-153">To run the procedure, copy and paste the following example into a new query window and click **Execute**.</span></span> <span data-ttu-id="06ce9-154">Notare che vengono mostrati metodi diversi per specificare i valori del parametro.</span><span class="sxs-lookup"><span data-stu-id="06ce9-154">Notice that different methods of specifying the parameter values are shown.</span></span>  
  
    ```sql
    EXECUTE HumanResources.uspGetEmployeesTest2 N'Ackerman', N'Pilar';  
    -- Or  
    EXEC HumanResources.uspGetEmployeesTest2 @LastName = N'Ackerman', @FirstName = N'Pilar';  
    GO  
    -- Or  
    EXECUTE HumanResources.uspGetEmployeesTest2 @FirstName = N'Pilar', @LastName = N'Ackerman';  
    GO
    ```  
  
## <a name="see-also"></a><span data-ttu-id="06ce9-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06ce9-155">See Also</span></span>  
 [<span data-ttu-id="06ce9-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06ce9-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  