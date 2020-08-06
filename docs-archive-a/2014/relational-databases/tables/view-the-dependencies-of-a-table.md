---
title: Visualizzare le dipendenze di una tabella | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table dependencies [SQL Server]
- dependencies [SQL Server], tables
- displaying dependences
- viewing dependencies
ms.assetid: c4351ef5-e7d0-46e7-8367-88695e9974f8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f54b913124cdaa8a7dfeebac01ba070cc37d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638334"
---
# <a name="view-the-dependencies-of-a-table"></a><span data-ttu-id="d4276-102">Visualizzare le dipendenze di una tabella</span><span class="sxs-lookup"><span data-stu-id="d4276-102">View the Dependencies of a Table</span></span>
  <span data-ttu-id="d4276-103">Le dipendenze di una tabella possono essere visualizzate in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4276-103">You can view a table's dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d4276-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d4276-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d4276-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d4276-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d4276-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d4276-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d4276-107">**Per visualizzare le dipendenze di una tabella:**</span><span class="sxs-lookup"><span data-stu-id="d4276-107">**To view a table's dependencies, using:**</span></span>  
  
     [<span data-ttu-id="d4276-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d4276-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d4276-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d4276-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d4276-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d4276-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d4276-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d4276-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d4276-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d4276-112">Permissions</span></span>  
 <span data-ttu-id="d4276-113">Sono richieste l'autorizzazione VIEW DEFINITION sul database e l'autorizzazione SELECT su sys.sql_expression_dependencies per il database.</span><span class="sxs-lookup"><span data-stu-id="d4276-113">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="d4276-114">L'autorizzazione SELECT è concessa per impostazione predefinita solo ai membri del ruolo predefinito del database di db_owner.</span><span class="sxs-lookup"><span data-stu-id="d4276-114">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="d4276-115">Quando le autorizzazioni SELECT e VIEW DEFINITION vengono concesse a un altro utente, l'utente autorizzato può visualizzare tutte le dipendenze nel database.</span><span class="sxs-lookup"><span data-stu-id="d4276-115">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d4276-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d4276-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-table"></a><span data-ttu-id="d4276-117">Per visualizzare le dipendenze di una tabella</span><span class="sxs-lookup"><span data-stu-id="d4276-117">To view the dependencies of a table</span></span>  
  
1.  <span data-ttu-id="d4276-118">In **Esplora oggetti**espandere **Database**, espandere un database e quindi espandere **Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="d4276-118">In **Object Explorer**, expand **Databases**, expand a database, and then expand **Tables**.</span></span>  
  
2.  <span data-ttu-id="d4276-119">Fare clic con il pulsante destro del mouse su una tabella e quindi scegliere **Visualizza dipendenze**.</span><span class="sxs-lookup"><span data-stu-id="d4276-119">Right-click a table, and then click **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="d4276-120">Nella finestra di dialogo **Dipendenze oggetti** _\<object name>_ selezionare **Oggetti che dipendono da** _\<object name>_ o **Oggetti da cui** _\<object name>_ **dipende**.</span><span class="sxs-lookup"><span data-stu-id="d4276-120">In the **Object Dependencies**_\<object name>_ dialog box, select either **Objects that depend on** _\<object name>_, or **Objects on which**_\<object name>_**depends**.</span></span>  
  
4.  <span data-ttu-id="d4276-121">Selezionare un oggetto nella griglia **Dipendenze** .</span><span class="sxs-lookup"><span data-stu-id="d4276-121">Select an object in the **Dependencies** grid.</span></span> <span data-ttu-id="d4276-122">Il tipo di oggetto, ad esempio "Trigger" o "Stored procedure", viene visualizzato nella casella **Tipo** .</span><span class="sxs-lookup"><span data-stu-id="d4276-122">The type of object (such as "Trigger" or "Stored Procedure"), appears in the **Type** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d4276-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d4276-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-objects-that-depend-on-a-table"></a><span data-ttu-id="d4276-124">Per visualizzare gli oggetti che dipendono da una tabella.</span><span class="sxs-lookup"><span data-stu-id="d4276-124">To view the objects that depend on a table</span></span>  
  
1.  <span data-ttu-id="d4276-125">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4276-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d4276-126">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d4276-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d4276-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d4276-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');   
    GO  
  
    ```  
  
#### <a name="to-view-the-objects-on-which-a-table-depends"></a><span data-ttu-id="d4276-128">Per visualizzare gli oggetti dai quali dipende una tabella.</span><span class="sxs-lookup"><span data-stu-id="d4276-128">To view the objects on which a table depends</span></span>  
  
1.  <span data-ttu-id="d4276-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4276-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d4276-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d4276-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d4276-131">Nell'esempio seguente restituire gli oggetti che dipendono dalla tabella `Production.Product`.</span><span class="sxs-lookup"><span data-stu-id="d4276-131">The following example returns the objects that depend on the table `Production.Product`.</span></span> <span data-ttu-id="d4276-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d4276-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referenced_id = OBJECT_ID(N'Production.Product');   
    GO  
  
    ```  
  
 <span data-ttu-id="d4276-133">Per alte informazioni, vedere [Sys. sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="d4276-133">For additional information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span></span>  
  
  
