---
title: Rinominare una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], renaming
- renaming stored procedures
ms.assetid: 5d2e4c68-7e0b-4405-8919-f5b203e46770
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02e1acb528a32ef242e160e0ce5dd0267237c876
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638364"
---
# <a name="rename-a-stored-procedure"></a><span data-ttu-id="4743e-102">Rinominare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="4743e-102">Rename a Stored Procedure</span></span>
  <span data-ttu-id="4743e-103">In questo argomento viene descritto come rinominare una stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4743e-103">This topic describes how to rename a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4743e-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4743e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4743e-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4743e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4743e-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4743e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4743e-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4743e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4743e-108">**Per rinominare una stored procedure tramite:**</span><span class="sxs-lookup"><span data-stu-id="4743e-108">**To rename a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="4743e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4743e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4743e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4743e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4743e-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4743e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4743e-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4743e-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4743e-113">I nomi delle procedure devono essere conformi alle regole per gli [identificatori](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="4743e-113">Procedure names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="4743e-114">La ridenominazione di una stored procedure non comporta la modifica del nome dell'oggetto corrispondente nella colonna di definizione della vista del catalogo **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="4743e-114">Renaming a stored procedure will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="4743e-115">È pertanto consigliabile evitare di rinominare questo tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="4743e-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="4743e-116">In alternativa, eliminare e ricreare la stored procedure con il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="4743e-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="4743e-117">La modifica del nome o della definizione di una stored procedure può causare un errore degli oggetti dipendenti se questi non vengono aggiornati in base alle modifiche apportate alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4743e-117">Changing the name or definition of a procedure can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the procedure.</span></span> <span data-ttu-id="4743e-118">Per altre informazioni, vedere [Visualizzare le dipendenze di una stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="4743e-118">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4743e-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4743e-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4743e-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4743e-120">Permissions</span></span>  
 <span data-ttu-id="4743e-121">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="4743e-121">CREATE PROCEDURE</span></span>  
 <span data-ttu-id="4743e-122">Sono richieste l'autorizzazione CREATE PROCEDURE per il database e ALTER per lo schema in cui viene creata la procedura. In alternativa, è richiesta l'appartenenza al ruolo predefinito del database **db_ddladmin**.</span><span class="sxs-lookup"><span data-stu-id="4743e-122">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created, or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
 <span data-ttu-id="4743e-123">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="4743e-123">ALTER PROCEDURE</span></span>  
 <span data-ttu-id="4743e-124">È richiesta l'autorizzazione ALTER per la procedura o l'appartenenza al ruolo predefinito **db_ddladmin** del database.</span><span class="sxs-lookup"><span data-stu-id="4743e-124">Requires ALTER permission on the procedure or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4743e-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4743e-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="4743e-126">Per rinominare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="4743e-126">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="4743e-127">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="4743e-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4743e-128">Espandere **Database**, espandere il database a cui appartiene la stored procedure, quindi espandere **Programmabilità**.</span><span class="sxs-lookup"><span data-stu-id="4743e-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="4743e-129">[Determinare le dipendenze della stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="4743e-129">[Determine the dependencies of the stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
4.  <span data-ttu-id="4743e-130">Espandere **Stored Procedures**, fare clic con il pulsante destro del mouse sulla procedura da rinominare e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="4743e-130">Expand **Stored Procedures**, right-click the procedure to rename, and then click **Rename**.</span></span>  
  
5.  <span data-ttu-id="4743e-131">Modificare il nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4743e-131">Modify the procedure name.</span></span>  
  
6.  <span data-ttu-id="4743e-132">Modificare il nome della stored procedure in qualsiasi oggetto dipendente o script che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="4743e-132">Modify the procedure name referenced in any dependent objects or scripts.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4743e-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4743e-133">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="4743e-134">Per rinominare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="4743e-134">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="4743e-135">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4743e-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4743e-136">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4743e-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4743e-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4743e-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4743e-138">In questo esempio viene illustrato come rinominare una stored procedure eliminandola e ricreandola con un nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="4743e-138">This example shows how to rename a procedure by dropping the procedure and re-creating the procedure with a new name.</span></span> <span data-ttu-id="4743e-139">Nel primo esempio si crea la stored procedure `'HumanResources.uspGetAllEmployeesTest`,</span><span class="sxs-lookup"><span data-stu-id="4743e-139">The first example creates the stored procedure `'HumanResources.uspGetAllEmployeesTest`.</span></span> <span data-ttu-id="4743e-140">nel secondo esempio la stored procedure viene rinominata in `HumanResources.uspEveryEmployeeTest`.</span><span class="sxs-lookup"><span data-stu-id="4743e-140">The second example renames the stored procedure to `HumanResources.uspEveryEmployeeTest`.</span></span>  
  
```sql  
--Create the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspGetAllEmployeesTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
  
--Rename the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspEveryEmployeeTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4743e-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4743e-141">See Also</span></span>  
 <span data-ttu-id="4743e-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4743e-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span></span>  
 <span data-ttu-id="4743e-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4743e-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="4743e-144">[Creazione di una stored procedure](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="4743e-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="4743e-145">[Modificare una stored procedure](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="4743e-145">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="4743e-146">[Eliminare una stored procedure](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="4743e-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="4743e-147">[Visualizzare la definizione di una stored procedure](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="4743e-147">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="4743e-148">Visualizzare le dipendenze di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="4743e-148">View the Dependencies of a Stored Procedure</span></span>](view-the-dependencies-of-a-stored-procedure.md)  
  
  
