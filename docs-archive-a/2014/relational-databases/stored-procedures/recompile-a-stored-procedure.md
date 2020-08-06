---
title: Ricompilare una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- sp_recompile
- WITH RECOMPILE clause
- recompiling stored procedures
- stored procedures [SQL Server], recompiling
ms.assetid: b90deb27-0099-4fe7-ba60-726af78f7c18
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a9bc0e1d4baecb7f4c66b83b57081ed3131123d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638367"
---
# <a name="recompile-a-stored-procedure"></a><span data-ttu-id="5b692-102">Ricompilare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="5b692-102">Recompile a Stored Procedure</span></span>
  <span data-ttu-id="5b692-103">In questo argomento viene descritto come ricompilare una stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b692-103">This topic describes how to recompile a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b692-104">Questa operazione può essere eseguita in tre modi: l' `WITH RECOMPILE` opzione nella definizione della stored procedure o quando viene chiamata la stored procedure, l'hint per la `RECOMPILE` query su singole istruzioni o l'utilizzo del `sp_recompile` stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="5b692-104">There are three ways to do this: `WITH RECOMPILE` option in the procedure definition or when the procedure is called, the `RECOMPILE` query hint on individual statements, or by using the `sp_recompile` system stored procedure.</span></span> <span data-ttu-id="5b692-105">Questo argomento illustra l'uso dell'opzione WITH RECOMPILE quando si crea una definizione di stored procedure e si esegue una stored procedure esistente.</span><span class="sxs-lookup"><span data-stu-id="5b692-105">This topic describes using the WITH RECOMPILE option when creating a procedure definition and executing an existing procedure.</span></span> <span data-ttu-id="5b692-106">Descrive anche l'uso della stored procedure di sistema sp_recompile per ricompilare una stored procedure esistente.</span><span class="sxs-lookup"><span data-stu-id="5b692-106">It also describes using the sp_recompile system stored procedure to recompile an existing procedure.</span></span>  
  
 <span data-ttu-id="5b692-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5b692-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b692-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5b692-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b692-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="5b692-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5b692-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b692-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b692-111">**Per ricompilare una stored procedure tramite:**</span><span class="sxs-lookup"><span data-stu-id="5b692-111">**To recompile a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="5b692-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b692-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b692-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5b692-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5b692-114">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="5b692-114">Recommendations</span></span>  
  
-   <span data-ttu-id="5b692-115">Quando una stored procedure viene compilata per la prima volta o viene ricompilata, il piano di query della stored procedure viene ottimizzato per lo stato corrente del database e dei relativi oggetti.</span><span class="sxs-lookup"><span data-stu-id="5b692-115">When a procedure is compiled for the first time or recompiled, the procedure's query plan is optimized for the current state of the database and its objects.</span></span> <span data-ttu-id="5b692-116">Se i dati o la struttura di un database vengono modificati significativamente, con la ricompilazione di una stored procedure viene aggiornato e ottimizzato il piano di query della stored procedure per tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="5b692-116">If a database undergoes significant changes to its data or structure, recompiling a procedure updates and optimizes the procedure's query plan for those changes.</span></span> <span data-ttu-id="5b692-117">Ciò può migliorare le prestazioni di elaborazione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-117">This can improve the procedure's processing performance.</span></span>  
  
-   <span data-ttu-id="5b692-118">In alcuni casi la ricompilazione della stored procedure deve essere forzata, in altri invece avviene automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5b692-118">There are times when procedure recompilation must be forced and other times when it occurs automatically.</span></span> <span data-ttu-id="5b692-119">La ricompilazione automatica ha luogo a ogni riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b692-119">Automatic recompiling occurs whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted.</span></span> <span data-ttu-id="5b692-120">Si verifica inoltre se vengono apportate modifiche alla progettazione fisica di una tabella sottostante a cui fa riferimento la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-120">It also occurs if an underlying table referenced by the procedure has undergone physical design changes.</span></span>  
  
-   <span data-ttu-id="5b692-121">È opportuno forzare la ricompilazione di una stored procedure anche per rispondere a un eventuale sniffing dei parametri riscontrato durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="5b692-121">Another reason to force a procedure to recompile is to counteract the "parameter sniffing" behavior of procedure compilation.</span></span> <span data-ttu-id="5b692-122">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue le stored procedure, nella generazione del piano di query rientrano tutti i valori di parametri utilizzati dalla stored procedure durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="5b692-122">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes procedures, any parameter values that are used by the procedure when it compiles are included as part of generating the query plan.</span></span> <span data-ttu-id="5b692-123">Se tali valori rappresentano quelli standard utilizzati per le chiamate successive della stored procedure, questa beneficerà del piano di query a ogni compilazione ed esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5b692-123">If these values represent the typical ones with which the procedure is subsequently called, then the procedure benefits from the query plan every time that it compiles and executes.</span></span> <span data-ttu-id="5b692-124">Se i valori dei parametri della stored procedure sono spesso atipici, le prestazioni possono migliorare con la forzatura di una ricompilazione della stored procedure e un nuovo piano basato su valori dei parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="5b692-124">If parameter values on the procedure are frequently atypical, forcing a recompile of the procedure and a new plan based on different parameter values can improve performance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5b692-125">presenta la ricompilazione di stored procedure a livello di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5b692-125">features statement-level recompilation of procedures.</span></span> <span data-ttu-id="5b692-126">Quando in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono ricompilate le stored procedure, in realtà viene compilata solo l'istruzione che ha causato la ricompilazione, anziché la stored procedure completa.</span><span class="sxs-lookup"><span data-stu-id="5b692-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompiles stored procedures, only the statement that caused the recompilation is compiled, instead of the complete procedure.</span></span>  
  
-   <span data-ttu-id="5b692-127">Se determinate query in una stored procedure utilizzano regolarmente valori atipici o temporanei, le prestazioni della stored procedure possono migliorare tramite l'utilizzo dell'hint per la query RECOMPILE all'interno delle query stesse.</span><span class="sxs-lookup"><span data-stu-id="5b692-127">If certain queries in a procedure regularly use atypical or temporary values, procedure performance can be improved by using the RECOMPILE query hint inside those queries.</span></span> <span data-ttu-id="5b692-128">Poiché vengono ricompilate solo le query che utilizzano l'hint per la query anziché la stored procedure completa, viene riprodotto il comportamento di ricompilazione a livello di istruzione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b692-128">Since only the queries using the query hint will be recompiled instead of the complete procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]'s statement-level recompilation behavior is mimicked.</span></span> <span data-ttu-id="5b692-129">Oltre all'utilizzo dei valori dei parametri correnti della stored procedure, l'hint per la query RECOMPILE utilizza i valori di qualsiasi variabile locale inclusa nella stored procedure quando si compila l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="5b692-129">But in addition to using the procedure's current parameter values, the RECOMPILE query hint also uses the values of any local variables inside the stored procedure when you compile the statement.</span></span> <span data-ttu-id="5b692-130">Per altre informazioni, vedere [Hint per la query (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="5b692-130">For more information, see [Query Hint (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b692-131">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b692-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b692-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5b692-132">Permissions</span></span>  
 <span data-ttu-id="5b692-133">`WITH RECOMPILE`Opzione</span><span class="sxs-lookup"><span data-stu-id="5b692-133">`WITH RECOMPILE` Option</span></span>  
 <span data-ttu-id="5b692-134">Se si utilizza questa opzione alla creazione della definizione della stored procedure, è necessario disporre dell'autorizzazione CREATE PROCEDURE per il database e dell'autorizzazione ALTER per lo schema in cui verrà creata la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-134">If this option is used when the procedure definition is created, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="5b692-135">Se questa opzione viene utilizzata in un'istruzione EXECUTE, richiede autorizzazioni EXECUTE sulla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-135">If this option is used in an EXECUTE statement, it requires EXECUTE permissions on the procedure.</span></span> <span data-ttu-id="5b692-136">Le autorizzazioni non sono richieste per l'istruzione EXECUTE stessa, ma le autorizzazioni di esecuzione sono necessarie per la stored procedure a cui fa riferimento l'istruzione EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="5b692-136">Permissions are not required on the EXECUTE statement itself but execute permissions are required on the procedure referenced in the EXECUTE statement.</span></span> <span data-ttu-id="5b692-137">Per altre informazioni, vedere [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b692-137">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
 <span data-ttu-id="5b692-138">`RECOMPILE`Hint per la query</span><span class="sxs-lookup"><span data-stu-id="5b692-138">`RECOMPILE` Query Hint</span></span>  
 <span data-ttu-id="5b692-139">Questa funzionalità viene usata quando si crea la stored procedure e si include l'hint nelle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] nella stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-139">This feature is used when the procedure is created and the hint is included in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure.</span></span> <span data-ttu-id="5b692-140">È pertanto necessario disporre dell'autorizzazione CREATE PROCEDURE per il database e dell'autorizzazione ALTER per lo schema in cui la stored procedure viene creata.</span><span class="sxs-lookup"><span data-stu-id="5b692-140">Therefore, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="5b692-141">`sp_recompile`Stored procedure di sistema</span><span class="sxs-lookup"><span data-stu-id="5b692-141">`sp_recompile` System Stored Procedure</span></span>  
 <span data-ttu-id="5b692-142">È richiesta l'autorizzazione ALTER per la stored procedure specificata.</span><span class="sxs-lookup"><span data-stu-id="5b692-142">Requires ALTER permission on the specified procedure.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b692-143">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b692-143">Using Transact-SQL</span></span>  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="5b692-144">Per ricompilare una stored procedure utilizzando l'opzione WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="5b692-144">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="5b692-145">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b692-145">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b692-146">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5b692-146">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b692-147">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b692-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b692-148">In questo esempio seguente viene creata la definizione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-148">This example creates the procedure definition.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspProductByVendor', 'P' ) IS NOT NULL   
    DROP PROCEDURE dbo.uspProductByVendor;  
GO  
CREATE PROCEDURE dbo.uspProductByVendor @Name varchar(30) = '%'  
WITH RECOMPILE  
AS  
    SET NOCOUNT ON;  
    SELECT v.Name AS 'Vendor name', p.Name AS 'Product name'  
    FROM Purchasing.Vendor AS v   
    JOIN Purchasing.ProductVendor AS pv   
      ON v.BusinessEntityID = pv.BusinessEntityID   
    JOIN Production.Product AS p   
      ON pv.ProductID = p.ProductID  
    WHERE v.Name LIKE @Name;  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="5b692-149">Per ricompilare una stored procedure utilizzando l'opzione WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="5b692-149">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="5b692-150">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b692-150">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b692-151">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5b692-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b692-152">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b692-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b692-153">In questo esempio viene creata una stored procedure semplice tramite cui vengono restituiti tutti i dipendenti (per cui vengono indicati il nome e il cognome), le relative posizioni e i nomi dei reparti di appartenenza da una vista.</span><span class="sxs-lookup"><span data-stu-id="5b692-153">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="5b692-154">Successivamente, copiare e incollare il secondo esempio di codice nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b692-154">And then copy and paste the second code example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b692-155">Verrà eseguita la stored procedure e verrà ricompilato il piano di query della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-155">This executes the procedure and recompiles the procedure's query plan.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXECUTE HumanResources.uspGetAllEmployees WITH RECOMPILE;  
GO  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-sp_recompile"></a><span data-ttu-id="5b692-156">Per ricompilare una stored procedure utilizzando sp_recompile</span><span class="sxs-lookup"><span data-stu-id="5b692-156">To recompile a stored procedure by using sp_recompile</span></span>  
  
1.  <span data-ttu-id="5b692-157">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b692-157">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b692-158">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5b692-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b692-159">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b692-159">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b692-160">In questo esempio viene creata una stored procedure semplice tramite cui vengono restituiti tutti i dipendenti (per cui vengono indicati il nome e il cognome), le relative posizioni e i nomi dei reparti di appartenenza da una vista.</span><span class="sxs-lookup"><span data-stu-id="5b692-160">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="5b692-161">Successivamente, copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b692-161">Then, copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b692-162">La stored procedure non verrà eseguita, ma contrassegnata per la ricompilazione in modo che il relativo piano di query venga aggiornata alla successiva esecuzione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5b692-162">This does not execute the procedure but it does mark the procedure to be recompiled so that its query plan is updated the next time that the procedure is executed.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_recompile N'HumanResources.uspGetAllEmployees';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b692-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b692-163">See Also</span></span>  
 <span data-ttu-id="5b692-164">[Creazione di una stored procedure](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5b692-164">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5b692-165">[Modificare una stored procedure](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5b692-165">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5b692-166">[Rinominare una stored procedure](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5b692-166">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5b692-167">[Visualizzare la definizione di una stored procedure](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5b692-167">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5b692-168">[Visualizzare le dipendenze di una stored procedure](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5b692-168">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="5b692-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b692-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
