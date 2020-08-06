---
title: Visualizzare o modificare le proprietà di un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- displaying databases
- database viewing [SQL Server]
- databases [SQL Server], viewing
- viewing databases
ms.assetid: 9e8ac097-84b7-46c7-85e3-c1e79f94d747
author: stevestein
ms.author: sstein
ms.openlocfilehash: d6aee7503ca02d47575be4e8103641f61d9696d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724743"
---
# <a name="view-or-change-the-properties-of-a-database"></a><span data-ttu-id="55b3c-102">Visualizzare o modificare le proprietà di un database</span><span class="sxs-lookup"><span data-stu-id="55b3c-102">View or Change the Properties of a Database</span></span>
  <span data-ttu-id="55b3c-103">In questo argomento si illustra come visualizzare o modificare le proprietà di un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55b3c-103">This topic describes how to view or change the properties of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="55b3c-104">Dopo aver modificato la proprietà di un database, la modifica diventa effettiva immediatamente.</span><span class="sxs-lookup"><span data-stu-id="55b3c-104">After you change a database property, the modification takes effect immediately.</span></span>  
  
 <span data-ttu-id="55b3c-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="55b3c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="55b3c-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="55b3c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="55b3c-107">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="55b3c-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="55b3c-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="55b3c-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="55b3c-109">**Per visualizzare o modificare le proprietà di un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="55b3c-109">**To view or change the properties of a database, using:**</span></span>  
  
     [<span data-ttu-id="55b3c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55b3c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="55b3c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55b3c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="55b3c-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="55b3c-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="55b3c-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="55b3c-113">Recommendations</span></span>  
  
-   <span data-ttu-id="55b3c-114">Se l'opzione AUTO_CLOSE è impostata su ON, alcune colonne nella vista del catalogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) e della funzione DATABASEPROPERTYEX restituiranno NULL perché il database non è disponibile per il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="55b3c-114">When AUTO_CLOSE is ON, some columns in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view and DATABASEPROPERTYEX function will return NULL because the database is unavailable to retrieve the data.</span></span> <span data-ttu-id="55b3c-115">Per risolvere questo problema, eseguire un'istruzione USE per aprire il database.</span><span class="sxs-lookup"><span data-stu-id="55b3c-115">To resolve this, execute a USE statement to open the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="55b3c-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="55b3c-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="55b3c-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="55b3c-117">Permissions</span></span>  
 <span data-ttu-id="55b3c-118">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="55b3c-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="55b3c-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55b3c-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-properties-of-a-database"></a><span data-ttu-id="55b3c-120">Per visualizzare o modificare le proprietà di un database</span><span class="sxs-lookup"><span data-stu-id="55b3c-120">To view or change the properties of a database</span></span>  
  
1.  <span data-ttu-id="55b3c-121">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="55b3c-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="55b3c-122">Espandere **Database**, fare clic con il pulsante destro del mouse sul database da visualizzare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-122">Expand **Databases**, right-click the database to view, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="55b3c-123">Nella finestra di dialogo **Proprietà database** selezionare una pagina per visualizzare le informazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="55b3c-123">In the **Database Properties** dialog box, select a page to view the corresponding information.</span></span> <span data-ttu-id="55b3c-124">Selezionare la pagina **File** , ad esempio, per visualizzare le informazioni sui file di dati e di log.</span><span class="sxs-lookup"><span data-stu-id="55b3c-124">For example, select the **Files** page to view data and log file information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="55b3c-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55b3c-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-property-of-a-database-by-using-databasepropertyex"></a><span data-ttu-id="55b3c-126">Per visualizzare una proprietà di un database tramite DATABASEPROPERTYEX</span><span class="sxs-lookup"><span data-stu-id="55b3c-126">To view a property of a database by using DATABASEPROPERTYEX</span></span>  
  
1.  <span data-ttu-id="55b3c-127">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55b3c-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55b3c-128">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55b3c-129">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="55b3c-130">Questo esempio usa la funzione di sistema [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) per restituire lo stato dell'opzione di database AUTO_SHRINK nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55b3c-130">This example uses the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) system function to return the status of the AUTO_SHRINK database option in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="55b3c-131">Un valore restituito pari a 1 indica che l'opzione è impostata su ON, mentre un valore restituito pari a 0 indica che l'opzione è impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="55b3c-131">A return value of 1 means that the option is set to ON, and a return value of 0 means that the option is set to OFF.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT DATABASEPROPERTYEX('AdventureWorks2012', 'IsAutoShrink');  
GO  
  
```  
  
#### <a name="to-view-the-properties-of-a-database-by-querying-sysdatabases"></a><span data-ttu-id="55b3c-132">Per visualizzare le proprietà di un database eseguendo una query su sys.databases</span><span class="sxs-lookup"><span data-stu-id="55b3c-132">To view the properties of a database by querying sys.databases</span></span>  
  
1.  <span data-ttu-id="55b3c-133">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55b3c-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55b3c-134">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55b3c-135">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="55b3c-136">In questo esempio si esegue una query sulla vista del catalogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) per visualizzare diverse proprietà del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55b3c-136">This example queries the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to view several properties of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="55b3c-137">In questo esempio viene restituito il numero ID del database (`database_id`), se il database è di sola lettura o di lettura e scrittura (`is_read_only`), le regole di confronto per il database (`collation_name`), nonché il livello di compatibilità del database (`compatibility_level`).</span><span class="sxs-lookup"><span data-stu-id="55b3c-137">This example returns the database ID number (`database_id`), whether the database is read-only or read-write (`is_read_only`), the collation for the database (`collation_name`), and the database compatibility level (`compatibility_level`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT database_id, is_read_only, collation_name, compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-properties-of-a-database"></a><span data-ttu-id="55b3c-138">Per modificare le proprietà di un database</span><span class="sxs-lookup"><span data-stu-id="55b3c-138">To change the properties of a database</span></span>  
  
1.  <span data-ttu-id="55b3c-139">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55b3c-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55b3c-140">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55b3c-141">Copiare e incollare l'esempio seguente nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="55b3c-141">Copy and paste the following example into the query window.</span></span> <span data-ttu-id="55b3c-142">Nell'esempio si determina lo stato di isolamento dello snapshot nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , si modifica lo stato della proprietà, quindi si verifica la modifica.</span><span class="sxs-lookup"><span data-stu-id="55b3c-142">The example determines the state of snapshot isolation on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, changes the state of the property, and then verifies the change.</span></span>  
  
     <span data-ttu-id="55b3c-143">Per determinare lo stato di isolamento dello snapshot, selezionare la prima istruzione `SELECT` e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-143">To determine the state of snapshot isolation, select the first `SELECT` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="55b3c-144">Per modificare lo stato di isolamento dello snapshot, selezionare la prima istruzione `ALTER DATABASE` e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-144">To change the state of snapshot isolation, select the `ALTER DATABASE` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="55b3c-145">Per verificare la modifica, selezionare la seconda istruzione `SELECT` e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="55b3c-145">To verify the change, select the second `SELECT` statement, and click **Execute**.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase9](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase9)]  
  
## <a name="see-also"></a><span data-ttu-id="55b3c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55b3c-146">See Also</span></span>  
 <span data-ttu-id="55b3c-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="55b3c-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="55b3c-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="55b3c-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="55b3c-149">[Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="55b3c-149">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="55b3c-150">[Mirroring del database di ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="55b3c-150">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="55b3c-151">[Livello di compatibilità ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="55b3c-151">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 [<span data-ttu-id="55b3c-152">Opzioni per file e filegroup ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="55b3c-152">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
  
