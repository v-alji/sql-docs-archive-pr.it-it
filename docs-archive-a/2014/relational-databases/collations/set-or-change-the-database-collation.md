---
title: Impostare o modificare le regole di confronto del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], database
- database collations [SQL Server]
ms.assetid: 1379605c-1242-4ac8-ab1b-e2a2b5b1f895
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d7f7c3e3ddba7ba0ea9701993dbe0fad3a8d975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637908"
---
# <a name="set-or-change-the-database-collation"></a><span data-ttu-id="a334d-102">Impostare o modificare le regole di confronto del database</span><span class="sxs-lookup"><span data-stu-id="a334d-102">Set or Change the Database Collation</span></span>
  <span data-ttu-id="a334d-103">In questo argomento viene descritto come impostare e modificare le regole di confronto del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a334d-103">This topic describes how set and change the database collation in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a334d-104">Se non viene specificata alcuna regola di confronto, vengono utilizzate le regole di confronto del server.</span><span class="sxs-lookup"><span data-stu-id="a334d-104">If no collation is specified, the server collation is used.</span></span>  
  
 <span data-ttu-id="a334d-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a334d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a334d-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a334d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a334d-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a334d-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a334d-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="a334d-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="a334d-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a334d-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a334d-110">**Per impostare o modificare le regole di confronto del database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="a334d-110">**To set or change the database collation, using:**</span></span>  
  
     [<span data-ttu-id="a334d-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a334d-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a334d-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a334d-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a334d-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a334d-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a334d-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a334d-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a334d-115">Le regole di confronto solo Unicode di Windows possono essere utilizzate solo con la clausola COLLATE per essere applicate ai tipi di dati `nchar`, `nvarchar` e `ntext` per i dati a livello di colonna e di espressione.</span><span class="sxs-lookup"><span data-stu-id="a334d-115">Windows Unicode-only collations can only be used with the COLLATE clause to apply collations to the `nchar`, `nvarchar`, and `ntext` data types on column level and expression-level data.</span></span> <span data-ttu-id="a334d-116">Non è possibile utilizzarle con la clausola COLLATE per modificare le regole di confronto di un database o un'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="a334d-116">They cannot be used with the COLLATE clause to change the collation of a database or server instance.</span></span>  
  
-   <span data-ttu-id="a334d-117">Se le regole di confronto specificate o adottate dall'oggetto cui viene fatto riferimento utilizzano una tabella codici non supportata dai sistemi operativi Windows, nel [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="a334d-117">If the specified collation or the collation used by the referenced object uses a code page that is not supported by Windows, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] displays an error.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a334d-118">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="a334d-118">Recommendations</span></span>  
  
-   <span data-ttu-id="a334d-119">È possibile trovare i nomi delle regole di confronto supportate in [Windows_collation_name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) e [Nome delle regole di confronto di SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql); oppure è possibile usare la funzione di sistema [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a334d-119">You can find the supported collation names in [Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) and [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql); or you can use the [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) system function.</span></span>  
  
-   <span data-ttu-id="a334d-120">Quando si modificano le regole di confronto del database, è possibile modificare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a334d-120">When you change the database collation, you change the following:</span></span>  
  
    -   <span data-ttu-id="a334d-121">Qualsiasi `char`, `varchar`, `text`, `nchar`, `nvarchar` o colonna `ntext` nelle tabelle di sistema viene impostata sulle nuove regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="a334d-121">Any `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` columns in system tables are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="a334d-122">Tutti i parametri di tipo `char`, `varchar`, `text`, `nchar`, `nvarchar` o `ntext` e i valori scalari restituiti per le stored procedure e le funzioni definite dall'utente vengono modificati in base alle nuove regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="a334d-122">All existing `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` parameters and scalar return values for stored procedures and user-defined functions are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="a334d-123">I tipi di dati di sistema `char`, `varchar`, `text`, `nchar`, `nvarchar` o `ntext` e tutti i tipi di dati definiti dall'utente basati sui questi tipi di dati di sistema vengono modificati in base alle nuove regole di confronto predefinite.</span><span class="sxs-lookup"><span data-stu-id="a334d-123">The `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` system data types, and all user-defined data types based on these system data types, are changed to the new default collation.</span></span>  
  
-   <span data-ttu-id="a334d-124">È possibile modificare le regole di confronto di qualsiasi nuovo oggetto creato in un database utente utilizzando la clausola COLLATE dell'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a334d-124">You can change the collation of any new objects that are created in a user database by using the COLLATE clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="a334d-125">Questa istruzione non consente di modificare le regole di confronto delle colonne delle tabelle definite dall'utente esistenti.</span><span class="sxs-lookup"><span data-stu-id="a334d-125">This statement does not change the collation of the columns in any existing user-defined tables.</span></span> <span data-ttu-id="a334d-126">Per modificare le regole di confronto delle colonne, è necessario utilizzare la clausola COLLATE dell'istruzione [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a334d-126">These can be changed by using the COLLATE clause of [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a334d-127">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a334d-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a334d-128">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a334d-128">Permissions</span></span>  
 <span data-ttu-id="a334d-129">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="a334d-129">CREATE DATABASE</span></span>  
 <span data-ttu-id="a334d-130">È richiesta l'autorizzazione CREATE DATABASE nel database **Master** oppure l'autorizzazione create any database o ALTER ANY database.</span><span class="sxs-lookup"><span data-stu-id="a334d-130">Requires CREATE DATABASE permission in the **master** database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="a334d-131">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="a334d-131">ALTER DATABASE</span></span>  
 <span data-ttu-id="a334d-132">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="a334d-132">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a334d-133">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a334d-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-or-change-the-database-collation"></a><span data-ttu-id="a334d-134">Per impostare o modificare le regole di confronto del database</span><span class="sxs-lookup"><span data-stu-id="a334d-134">To set or change the database collation</span></span>  
  
1.  <span data-ttu-id="a334d-135">In **Esplora oggetti**connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], espandere tale istanza, quindi espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="a334d-135">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="a334d-136">Se si crea un nuovo database, fare clic con il pulsante destro del mouse su **Database** , quindi fare clic su **Nuovo database**.</span><span class="sxs-lookup"><span data-stu-id="a334d-136">If you are creating a new database, right-click **Databases** and then click **New Database**.</span></span> <span data-ttu-id="a334d-137">Se non si vuole usare le regole di confronto predefinite, fare clic sulla pagina **Opzioni** e selezionare le regole di confronto dall'elenco a discesa **Regole di confronto** .</span><span class="sxs-lookup"><span data-stu-id="a334d-137">If you do not want the default collation, click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
     <span data-ttu-id="a334d-138">In alternativa, se il database esiste già, fare clic con il pulsante destro del mouse sul database desiderato e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a334d-138">Alternatively, if the database already exists, right-click the database that you want and click **Properties**.</span></span> <span data-ttu-id="a334d-139">Fare clic sulla pagina **Opzioni** e selezionare le regole di confronto dall'elenco a discesa **Regole di confronto** .</span><span class="sxs-lookup"><span data-stu-id="a334d-139">Click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
3.  <span data-ttu-id="a334d-140">Al termine dell'operazione scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="a334d-140">After you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a334d-141">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a334d-141">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-database-collation"></a><span data-ttu-id="a334d-142">Per impostare le regole di confronto del database</span><span class="sxs-lookup"><span data-stu-id="a334d-142">To set the database collation</span></span>  
  
1.  <span data-ttu-id="a334d-143">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a334d-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a334d-144">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a334d-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a334d-145">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a334d-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a334d-146">In questo esempio viene mostrato come utilizzare la clausola [COLLATE](/sql/t-sql/statements/collations) per specificare un nome delle regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="a334d-146">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause to specify a collation name.</span></span> <span data-ttu-id="a334d-147">Nell'esempio viene creato l'elemento `MyOptionsTest` del database che utilizza le regole di confronto `Latin1_General_100_CS_AS_SC` .</span><span class="sxs-lookup"><span data-stu-id="a334d-147">The example creates the database `MyOptionsTest` that uses the `Latin1_General_100_CS_AS_SC` collation.</span></span> <span data-ttu-id="a334d-148">Dopo aver creato il database, eseguire l'istruzione `SELECT` per verificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="a334d-148">After you create the database, execute the `SELECT` statement to verify the setting.</span></span>  
  
```sql  
USE master;  
GO  
IF DB_ID (N'MyOptionsTest') IS NOT NULL  
DROP DATABASE MyOptionsTest;  
GO  
CREATE DATABASE MyOptionsTest  
COLLATE Latin1_General_100_CS_AS_SC;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
#### <a name="to-change-the-database-collation"></a><span data-ttu-id="a334d-149">Per modificare le regole di confronto del database</span><span class="sxs-lookup"><span data-stu-id="a334d-149">To change the database collation</span></span>  
  
1.  <span data-ttu-id="a334d-150">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a334d-150">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a334d-151">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a334d-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a334d-152">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a334d-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a334d-153">In questo esempio viene mostrato come utilizzare la clausola [COLLATE](/sql/t-sql/statements/collations) in un'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) per modificare il nome delle regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="a334d-153">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause in an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to change the collation name.</span></span> <span data-ttu-id="a334d-154">Eseguire l'istruzione `SELECT` per verificare la modifica.</span><span class="sxs-lookup"><span data-stu-id="a334d-154">Execute the `SELECT` statement to verify the change.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE MyOptionsTest  
COLLATE French_CI_AS ;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="a334d-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a334d-155">See Also</span></span>  
 <span data-ttu-id="a334d-156">[Regole di confronto e supporto Unicode](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="a334d-156">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="a334d-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="a334d-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="a334d-159">[Nome delle regole di confronto di SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-159">[SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="a334d-160">[Windows_collation_name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-160">[Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="a334d-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span><span class="sxs-lookup"><span data-stu-id="a334d-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span></span>  
 <span data-ttu-id="a334d-162">[Precedenza delle regole di confronto &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-162">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 <span data-ttu-id="a334d-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="a334d-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="a334d-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a334d-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="a334d-166">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a334d-166">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
