---
title: Sintassi Transact-SQL supportata da IntelliSense
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL IntelliSense
- IntelliSense [SQL Server], Transact-SQL syntax
ms.assetid: 194e8f4f-fd7e-4f32-a169-f23531128004
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d34fc79dd7817e64b34b61083415477860ce97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717789"
---
# <a name="transact-sql-syntax-supported-by-intellisense"></a><span data-ttu-id="a6b74-102">Sintassi Transact-SQL supportata da IntelliSense</span><span class="sxs-lookup"><span data-stu-id="a6b74-102">Transact-SQL Syntax Supported by IntelliSense</span></span>
  <span data-ttu-id="a6b74-103">In questo argomento vengono descritti le istruzioni e gli elementi di sintassi [!INCLUDE[tsql](../../includes/tsql-md.md)] supportati da IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6b74-103">This topic describes the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and syntax elements that are supported by IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="statements-supported-by-intellisense"></a><span data-ttu-id="a6b74-104">Istruzioni supportate da IntelliSense</span><span class="sxs-lookup"><span data-stu-id="a6b74-104">Statements Supported by IntelliSense</span></span>  
 <span data-ttu-id="a6b74-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense supporta solo le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] di uso più frequente.</span><span class="sxs-lookup"><span data-stu-id="a6b74-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense supports only the most commonly used [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="a6b74-106">Alcune condizioni generali dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] potrebbero impedire il funzionamento di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a6b74-106">Some general [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor conditions might prevent IntelliSense from functioning.</span></span> <span data-ttu-id="a6b74-107">Per altre informazioni, vedere [Risoluzione dei problemi di IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="a6b74-107">For more information, see [Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6b74-108">IntelliSense non è disponibile per gli oggetti di database crittografati, ad esempio stored procedure o funzioni definite dall'utente crittografate.</span><span class="sxs-lookup"><span data-stu-id="a6b74-108">IntelliSense is not available for encrypted database objects, such as encrypted stored procedures or user-defined functions.</span></span> <span data-ttu-id="a6b74-109">Le funzionalità Guida relativa ai parametri e Informazioni rapide non sono disponibili per i parametri di stored procedure estese e per i tipi definiti dall'utente di Integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="a6b74-109">Parameter help and Quick Info are not available for the parameters of extended stored procedures and CLR Integration user-defined types.</span></span>  
  
### <a name="select-statement"></a><span data-ttu-id="a6b74-110">Istruzione SELECT</span><span class="sxs-lookup"><span data-stu-id="a6b74-110">SELECT Statement</span></span>  
 <span data-ttu-id="a6b74-111">L'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] offre supporto IntelliSense per gli elementi della sintassi seguenti nell'istruzione SELECT:</span><span class="sxs-lookup"><span data-stu-id="a6b74-111">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor provides IntelliSense support for the following syntax elements in the SELECT statement:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6b74-112">SELECT</span><span class="sxs-lookup"><span data-stu-id="a6b74-112">SELECT</span></span>|<span data-ttu-id="a6b74-113">WHERE</span><span class="sxs-lookup"><span data-stu-id="a6b74-113">WHERE</span></span>|  
|<span data-ttu-id="a6b74-114">FROM</span><span class="sxs-lookup"><span data-stu-id="a6b74-114">FROM</span></span>|<span data-ttu-id="a6b74-115">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="a6b74-115">ORDER BY</span></span>|  
|<span data-ttu-id="a6b74-116">HAVING</span><span class="sxs-lookup"><span data-stu-id="a6b74-116">HAVING</span></span>|<span data-ttu-id="a6b74-117">UNION</span><span class="sxs-lookup"><span data-stu-id="a6b74-117">UNION</span></span>|  
|<span data-ttu-id="a6b74-118">FOR</span><span class="sxs-lookup"><span data-stu-id="a6b74-118">FOR</span></span>|<span data-ttu-id="a6b74-119">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="a6b74-119">GROUP BY</span></span>|  
|<span data-ttu-id="a6b74-120">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="a6b74-120">TOP</span></span>|<span data-ttu-id="a6b74-121">OPTION (hint)</span><span class="sxs-lookup"><span data-stu-id="a6b74-121">OPTION (hint)</span></span>|  
  
### <a name="additional-transact-sql-statements-that-are-supported"></a><span data-ttu-id="a6b74-122">Istruzioni Transact-SQL aggiuntive supportate</span><span class="sxs-lookup"><span data-stu-id="a6b74-122">Additional Transact-SQL Statements That Are Supported</span></span>  
 <span data-ttu-id="a6b74-123">L'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] offre inoltre supporto IntelliSense per le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a6b74-123">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor also provides IntelliSense support for [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are shown in the following table.</span></span>  
  
|<span data-ttu-id="a6b74-124">Istruzione Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6b74-124">Transact-SQL statement</span></span>|<span data-ttu-id="a6b74-125">Sintassi supportata</span><span class="sxs-lookup"><span data-stu-id="a6b74-125">Syntax supported</span></span>|  
|-----------------------------|----------------------|  
|[<span data-ttu-id="a6b74-126">INSERT</span><span class="sxs-lookup"><span data-stu-id="a6b74-126">INSERT</span></span>](/sql/t-sql/statements/insert-transact-sql)|<span data-ttu-id="a6b74-127">Tutta la sintassi, eccetto la clausola *execute_statement* .</span><span class="sxs-lookup"><span data-stu-id="a6b74-127">All syntax, except the *execute_statement* clause.</span></span>|  
|[<span data-ttu-id="a6b74-128">UPDATE</span><span class="sxs-lookup"><span data-stu-id="a6b74-128">UPDATE</span></span>](/sql/t-sql/queries/update-transact-sql)|<span data-ttu-id="a6b74-129">Tutta la sintassi.</span><span class="sxs-lookup"><span data-stu-id="a6b74-129">All syntax.</span></span>|  
|[<span data-ttu-id="a6b74-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="a6b74-130">DELETE</span></span>](/sql/t-sql/statements/delete-transact-sql)|<span data-ttu-id="a6b74-131">Tutta la sintassi.</span><span class="sxs-lookup"><span data-stu-id="a6b74-131">All syntax.</span></span>|  
|[<span data-ttu-id="a6b74-132">DICHIARARE@local_variable</span><span class="sxs-lookup"><span data-stu-id="a6b74-132">DECLARE @local_variable</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)|<span data-ttu-id="a6b74-133">Tutta la sintassi.</span><span class="sxs-lookup"><span data-stu-id="a6b74-133">All syntax.</span></span>|  
|[<span data-ttu-id="a6b74-134">SET@local_variable</span><span class="sxs-lookup"><span data-stu-id="a6b74-134">SET @local_variable</span></span>](/sql/t-sql/language-elements/set-local-variable-transact-sql)|<span data-ttu-id="a6b74-135">Tutta la sintassi.</span><span class="sxs-lookup"><span data-stu-id="a6b74-135">All syntax.</span></span>|  
|[<span data-ttu-id="a6b74-136">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="a6b74-136">EXECUTE</span></span>](/sql/t-sql/language-elements/execute-transact-sql)|<span data-ttu-id="a6b74-137">Esecuzione di stored procedure e di funzioni definite dall'utente e di sistema.</span><span class="sxs-lookup"><span data-stu-id="a6b74-137">Execution of user-defined stored procedures, system stored procedures, user-defined functions, and system functions.</span></span>|  
|[<span data-ttu-id="a6b74-138">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="a6b74-138">CREATE TABLE</span></span>](/sql/t-sql/statements/create-table-transact-sql)|<span data-ttu-id="a6b74-139">Tutta la sintassi.</span><span class="sxs-lookup"><span data-stu-id="a6b74-139">All syntax.</span></span>|  
|[<span data-ttu-id="a6b74-140">CREATE VIEW</span><span class="sxs-lookup"><span data-stu-id="a6b74-140">CREATE VIEW</span></span>](/sql/t-sql/statements/create-view-transact-sql)|<span data-ttu-id="a6b74-141">Tutta la sintassi.</span><span class="sxs-lookup"><span data-stu-id="a6b74-141">All syntax.</span></span>|  
|[<span data-ttu-id="a6b74-142">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="a6b74-142">CREATE PROCEDURE</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)|<span data-ttu-id="a6b74-143">Tutta la sintassi, con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6b74-143">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="a6b74-144">Non è disponibile supporto IntelliSense per la clausola EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="a6b74-144">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="a6b74-145">Nella clausola AS IntelliSense supporta solo le istruzioni e la sintassi elencate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a6b74-145">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="a6b74-146">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="a6b74-146">ALTER PROCEDURE</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)|<span data-ttu-id="a6b74-147">Tutta la sintassi, con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6b74-147">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="a6b74-148">Non è disponibile supporto IntelliSense per la clausola EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="a6b74-148">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="a6b74-149">Nella clausola AS IntelliSense supporta solo le istruzioni e la sintassi elencate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a6b74-149">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="a6b74-150">USARE</span><span class="sxs-lookup"><span data-stu-id="a6b74-150">USE</span></span>](/sql/t-sql/language-elements/use-transact-sql)|<span data-ttu-id="a6b74-151">Tutta la sintassi.</span><span class="sxs-lookup"><span data-stu-id="a6b74-151">All syntax.</span></span>|  
  
## <a name="intellisense-in-supported-statements"></a><span data-ttu-id="a6b74-152">IntelliSense in istruzioni supportate</span><span class="sxs-lookup"><span data-stu-id="a6b74-152">IntelliSense in Supported Statements</span></span>  
 <span data-ttu-id="a6b74-153">Nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] IntelliSense supporta i seguenti elementi della sintassi quando vengono utilizzati in una delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] supportate:</span><span class="sxs-lookup"><span data-stu-id="a6b74-153">IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following syntax elements when they are used in one of the supported [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
-   <span data-ttu-id="a6b74-154">Tutti i tipi di join, ad esempio APPLY</span><span class="sxs-lookup"><span data-stu-id="a6b74-154">All join types, including APPLY</span></span>  
  
-   <span data-ttu-id="a6b74-155">PIVOT e UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="a6b74-155">PIVOT and UNPIVOT</span></span>  
  
-   <span data-ttu-id="a6b74-156">Riferimenti agli oggetti di database seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6b74-156">References to the following database objects:</span></span>  
  
    -   <span data-ttu-id="a6b74-157">Database e schemi</span><span class="sxs-lookup"><span data-stu-id="a6b74-157">Databases and schemas</span></span>  
  
    -   <span data-ttu-id="a6b74-158">Tabelle, viste, funzioni con valori di tabella ed espressioni di tabella</span><span class="sxs-lookup"><span data-stu-id="a6b74-158">Tables, views, table-valued functions, and table expressions</span></span>  
  
    -   <span data-ttu-id="a6b74-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="a6b74-159">Columns</span></span>  
  
    -   <span data-ttu-id="a6b74-160">Procedure e parametri di procedura</span><span class="sxs-lookup"><span data-stu-id="a6b74-160">Procedures and procedure parameters</span></span>  
  
    -   <span data-ttu-id="a6b74-161">Funzioni ed espressioni scalari</span><span class="sxs-lookup"><span data-stu-id="a6b74-161">Scalar functions and scalar expressions</span></span>  
  
    -   <span data-ttu-id="a6b74-162">Variabili locali</span><span class="sxs-lookup"><span data-stu-id="a6b74-162">Local variables</span></span>  
  
    -   <span data-ttu-id="a6b74-163">Espressioni di tabella comuni (CTE)</span><span class="sxs-lookup"><span data-stu-id="a6b74-163">Common table expressions (CTE)</span></span>  
  
-   <span data-ttu-id="a6b74-164">Oggetti di database cui viene fatto riferimento solo in istruzioni CREATE o ALTER nello script o nel batch, ma che non esistono nel database perché lo script o il batch non è ancora stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="a6b74-164">Database objects that are referenced only in CREATE or ALTER statements in the script or batch, but which do not exist in the database because the script or batch has not yet been run.</span></span> <span data-ttu-id="a6b74-165">Questi oggetti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6b74-165">These objects are as follows:</span></span>  
  
    -   <span data-ttu-id="a6b74-166">Tabelle e procedure specificate in un'istruzione CREATE TABLE o CREATE PROCEDURE nello script o nel batch.</span><span class="sxs-lookup"><span data-stu-id="a6b74-166">Tables and procedures that have been specified in a CREATE TABLE or CREATE PROCEDURE statement in the script or batch.</span></span>  
  
    -   <span data-ttu-id="a6b74-167">Modifiche a tabelle e procedure specificate in un'istruzione ALTER TABLE o ALTER PROCEDURE nello script o nel batch.</span><span class="sxs-lookup"><span data-stu-id="a6b74-167">Changes to tables and procedures that have been specified in an ALTER TABLE or ALTER PROCEDURE statement in the script or batch.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a6b74-168">IntelliSense non è disponibile per le colonne di un'istruzione CREATE VIEW fino a che non è stata eseguita l'istruzione CREATE VIEW.</span><span class="sxs-lookup"><span data-stu-id="a6b74-168">IntelliSense is not available for the columns of a CREATE VIEW statement until the CREATE VIEW statement has been executed.</span></span>  
  
 <span data-ttu-id="a6b74-169">IntelliSense non è disponibile per gli elementi elencati sopra quando vengono usati in altre istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6b74-169">IntelliSense is not provided for the previously listed elements when they are used in other [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="a6b74-170">Il supporto IntelliSense è ad esempio disponibile per i nomi di colonna utilizzati in un'istruzione SELECT, ma non per le colonne utilizzate nell'istruzione CREATE FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="a6b74-170">For example, there is IntelliSense support for column names that are used in a SELECT statement, but not for columns that are used in the CREATE FUNCTION statement.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a6b74-171">Esempi</span><span class="sxs-lookup"><span data-stu-id="a6b74-171">Examples</span></span>  
 <span data-ttu-id="a6b74-172">All'interno di uno script o di un batch [!INCLUDE[tsql](../../includes/tsql-md.md)] , nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] IntelliSense supporta solo le istruzioni e la sintassi elencate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a6b74-172">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports only the statements and syntax that are listed in this topic.</span></span> <span data-ttu-id="a6b74-173">Negli esempi di codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti sono mostrati le istruzioni e gli elementi della sintassi che IntelliSense supporta.</span><span class="sxs-lookup"><span data-stu-id="a6b74-173">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code examples show what statements and syntax elements IntelliSense supports.</span></span> <span data-ttu-id="a6b74-174">Ad esempio, nel batch seguente, IntelliSense è disponibile per l'istruzione `SELECT` quando è codificata da sola, ma non quando `SELECT` è contenuta in un'istruzione `CREATE FUNCTION` .</span><span class="sxs-lookup"><span data-stu-id="a6b74-174">For example, in the following batch, IntelliSense is available for the `SELECT` statement when it is coded by itself, but not when the `SELECT` is contained in a `CREATE FUNCTION` statement.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Name  
FROM Production.Product  
WHERE Name LIKE N'Road-250%' and Color = N'Red';  
GO  
CREATE FUNCTION Production.ufn_Red250 ()  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT Name  
    FROM AdventureWorks2012.Production.Product  
    WHERE Name LIKE N'Road-250%'  
      AND Color = N'Red'  
);GO  
```  
  
 <span data-ttu-id="a6b74-175">Questa funzionalità si applica anche ai set di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] nella clausola AS di un'istruzione CREATE PROCEDURE o ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="a6b74-175">This functionality also applies to the sets of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the AS clause of a CREATE PROCEDURE or ALTER PROCEDURE statement.</span></span>  
  
 <span data-ttu-id="a6b74-176">All'interno di uno script o un batch [!INCLUDE[tsql](../../includes/tsql-md.md)] , IntelliSense supporta gli oggetti che sono stati specificati in un'istruzione CREATE o ALTER, ma questi oggetti non esistono nel database perché le istruzioni non sono state eseguite.</span><span class="sxs-lookup"><span data-stu-id="a6b74-176">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense supports objects that have been specified in a CREATE or ALTER statement; however, these objects do not exist in the database because the statements have not been executed.</span></span> <span data-ttu-id="a6b74-177">È possibile ad esempio immettere nell'editor di query il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a6b74-177">For example, you might enter the following code in the Query Editor:</span></span>  
  
```  
USE MyTestDB;  
GO  
CREATE TABLE MyTable  
    (PrimaryKeyCol   INT PRIMARY KEY,  
    FirstNameCol      NVARCHAR(50),  
   LastNameCol       NVARCHAR(50));  
GO  
SELECT   
```  
  
 <span data-ttu-id="a6b74-178">Quando si digita `SELECT`, IntelliSense elenca **PrimaryKeyCol**, **FirstNameCol**e **LastNameCol** come possibili elementi dell'elenco di selezione, anche se lo script non è stato eseguito e `MyTable` non esiste ancora in `MyTestDB`.</span><span class="sxs-lookup"><span data-stu-id="a6b74-178">After you type `SELECT`, IntelliSense lists **PrimaryKeyCol**, **FirstNameCol**, and **LastNameCol** as possible elements in the select list, even if the script has not been executed and `MyTable` does not yet exist in `MyTestDB`.</span></span>  
  
  
