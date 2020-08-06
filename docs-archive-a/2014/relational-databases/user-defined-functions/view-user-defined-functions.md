---
title: Visualizzare funzioni definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.udfproperties.general.f1
- sql12.swb.functionproperties.general.f1
helpviewer_keywords:
- displaying user-defined functions
- viewing user-defined functions
- user-defined functions [SQL Server], viewing
- status information [SQL Server], user-defined functions
ms.assetid: a45dfab5-6384-4311-b935-2e23a70c5c10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5248f75540b72b489a7605b2cca34144dfcfedbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623095"
---
# <a name="view-user-defined-functions"></a><span data-ttu-id="2efef-102">Visualizzare le funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="2efef-102">View User-defined Functions</span></span>
  <span data-ttu-id="2efef-103">È possibile acquisire informazioni sulla definizione o le proprietà di una funzione definita dall'utente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2efef-103">You can gain information about the definition or properties of a user-defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2efef-104">Potrebbe essere necessario visualizzare la definizione della funzione per determinare come vengono derivati i dati dalle tabelle di origine o per visualizzare i dati definiti dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="2efef-104">You may need to see the definition of the function to understand how its data is derived from the source tables or to see the data defined by the function.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2efef-105">Se si cambia il nome di un oggetto a cui viene fatto riferimento da una funzione, è necessario modificare la funzione in modo che per il relativo testo venga fatto riferimento al nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="2efef-105">If you change the name of an object referenced by a function, you must modify that function so that its text reflects the new name.</span></span> <span data-ttu-id="2efef-106">Pertanto, prima di rinominare un oggetto, visualizzare le dipendenze dell'oggetto per determinare se la modifica proposta interessa eventuali funzioni.</span><span class="sxs-lookup"><span data-stu-id="2efef-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any functions are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="2efef-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2efef-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2efef-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2efef-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2efef-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2efef-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2efef-110">**Per acquisire informazioni su una funzione tramite:**</span><span class="sxs-lookup"><span data-stu-id="2efef-110">**To get information about a function, using:**</span></span>  
  
     [<span data-ttu-id="2efef-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2efef-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2efef-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2efef-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2efef-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2efef-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2efef-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2efef-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2efef-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2efef-115">Permissions</span></span>  
 <span data-ttu-id="2efef-116">L'uso di **sys.sql_expression_dependencies** per trovare tutte le dipendenze da una funzione richiede l'autorizzazione VIEW DEFINITION per il database e l'autorizzazione SELECT per **sys.sql_expression_dependencies** per il database.</span><span class="sxs-lookup"><span data-stu-id="2efef-116">Using **sys.sql_expression_dependencies** to find all the dependencies on a function requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="2efef-117">Le definizioni dell'oggetto di sistema, come quelle restituite in OBJECT_DEFINITION sono visibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="2efef-117">System object definitions, like the ones returned in OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2efef-118">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2efef-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-a-user-defined-functions-properties"></a><span data-ttu-id="2efef-119">Per mostrare le proprietà di una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="2efef-119">To show a user-defined function's properties</span></span>  
  
1.  <span data-ttu-id="2efef-120">In **Esplora oggetti**fare clic sul segno più accanto al database contenente la funzione in cui si desidera visualizzare le proprietà, quindi fare di nuovo clic sul segno più per espandere la cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="2efef-120">In **Object Explorer**, click the plus sign next to the database that contains the function to which you want to view the properties, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="2efef-121">Fare clic sul segno più per espandere la cartella **Funzioni** .</span><span class="sxs-lookup"><span data-stu-id="2efef-121">Click the plus sign to expand the **Functions** folder.</span></span>  
  
3.  <span data-ttu-id="2efef-122">Fare clic sul segno più per espandere la cartella che contiene la funzione di cui si desidera visualizzare le proprietà:</span><span class="sxs-lookup"><span data-stu-id="2efef-122">Click the plus sign to expand the folder that contains the function to which you want to view the properties:</span></span>  
  
    -   <span data-ttu-id="2efef-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="2efef-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="2efef-124">Funzione a valori scalari</span><span class="sxs-lookup"><span data-stu-id="2efef-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="2efef-125">Funzione di aggregazione</span><span class="sxs-lookup"><span data-stu-id="2efef-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="2efef-126">Fare clic con il pulsante destro del mouse sulla funzione di cui si vogliono visualizzare le proprietà e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2efef-126">Right-click the function of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="2efef-127">Le proprietà seguenti vengono visualizzate nella finestra di dialogo **Proprietà funzione -** _nome_funzione_.</span><span class="sxs-lookup"><span data-stu-id="2efef-127">The following properties appear in the **Function Properties -** _function_name_ dialog box.</span></span>  
  
     <span data-ttu-id="2efef-128">**Database**</span><span class="sxs-lookup"><span data-stu-id="2efef-128">**Database**</span></span>  
     <span data-ttu-id="2efef-129">Nome del database che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="2efef-129">The name of the database containing this function.</span></span>  
  
     <span data-ttu-id="2efef-130">**Server**</span><span class="sxs-lookup"><span data-stu-id="2efef-130">**Server**</span></span>  
     <span data-ttu-id="2efef-131">Nome dell'istanza del server corrente.</span><span class="sxs-lookup"><span data-stu-id="2efef-131">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="2efef-132">**Utente**</span><span class="sxs-lookup"><span data-stu-id="2efef-132">**User**</span></span>  
     <span data-ttu-id="2efef-133">Nome dell'utente della connessione.</span><span class="sxs-lookup"><span data-stu-id="2efef-133">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="2efef-134">**Data creazione**</span><span class="sxs-lookup"><span data-stu-id="2efef-134">**Created date**</span></span>  
     <span data-ttu-id="2efef-135">Visualizza la data di creazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="2efef-135">Displays the date the function was created.</span></span>  
  
     <span data-ttu-id="2efef-136">**Esegui come**</span><span class="sxs-lookup"><span data-stu-id="2efef-136">**Execute As**</span></span>  
     <span data-ttu-id="2efef-137">Contesto di esecuzione per la funzione.</span><span class="sxs-lookup"><span data-stu-id="2efef-137">Execution context for the function.</span></span>  
  
     <span data-ttu-id="2efef-138">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2efef-138">**Name**</span></span>  
     <span data-ttu-id="2efef-139">Nome della funzione corrente.</span><span class="sxs-lookup"><span data-stu-id="2efef-139">The name of the current function.</span></span>  
  
     <span data-ttu-id="2efef-140">**Schema**</span><span class="sxs-lookup"><span data-stu-id="2efef-140">**Schema**</span></span>  
     <span data-ttu-id="2efef-141">Visualizza lo schema proprietario della funzione.</span><span class="sxs-lookup"><span data-stu-id="2efef-141">Displays the schema that owns the function.</span></span>  
  
     <span data-ttu-id="2efef-142">**Oggetto di sistema**</span><span class="sxs-lookup"><span data-stu-id="2efef-142">**System object**</span></span>  
     <span data-ttu-id="2efef-143">Indica se la funzione è un oggetto di sistema.</span><span class="sxs-lookup"><span data-stu-id="2efef-143">Indicates whether the function is a system object.</span></span> <span data-ttu-id="2efef-144">I valori sono True e False.</span><span class="sxs-lookup"><span data-stu-id="2efef-144">Values are True and False.</span></span>  
  
     <span data-ttu-id="2efef-145">**ANSI NULLs**</span><span class="sxs-lookup"><span data-stu-id="2efef-145">**ANSI NULLs**</span></span>  
     <span data-ttu-id="2efef-146">Indica se l'oggetto è stato creato con l'opzione ANSI NULLs.</span><span class="sxs-lookup"><span data-stu-id="2efef-146">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="2efef-147">**Crittografata**</span><span class="sxs-lookup"><span data-stu-id="2efef-147">**Encrypted**</span></span>  
     <span data-ttu-id="2efef-148">Indica se la funzione è crittografata.</span><span class="sxs-lookup"><span data-stu-id="2efef-148">Indicates whether the function is encrypted.</span></span> <span data-ttu-id="2efef-149">I valori sono True e False.</span><span class="sxs-lookup"><span data-stu-id="2efef-149">Values are True and False.</span></span>  
  
     <span data-ttu-id="2efef-150">**Tipo di funzione**</span><span class="sxs-lookup"><span data-stu-id="2efef-150">**Function Type**</span></span>  
     <span data-ttu-id="2efef-151">Tipo della funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2efef-151">The type of user defined function.</span></span>  
  
     <span data-ttu-id="2efef-152">**Identificatore delimitato**</span><span class="sxs-lookup"><span data-stu-id="2efef-152">**Quoted identifier**</span></span>  
     <span data-ttu-id="2efef-153">Indica se l'oggetto è stato creato con l'opzione quoted identifier.</span><span class="sxs-lookup"><span data-stu-id="2efef-153">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="2efef-154">**Associata a schema**</span><span class="sxs-lookup"><span data-stu-id="2efef-154">**Schema bound**</span></span>  
     <span data-ttu-id="2efef-155">Indica se la funzione è associata allo schema.</span><span class="sxs-lookup"><span data-stu-id="2efef-155">Indicates whether the function is schema-bound.</span></span> <span data-ttu-id="2efef-156">I valori sono True e False.</span><span class="sxs-lookup"><span data-stu-id="2efef-156">Values are True and False.</span></span> <span data-ttu-id="2efef-157">Per informazioni sulle funzioni associate a schema, vedere la sezione relativa a SCHEMABINDING in [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2efef-157">For information about schema-bound functions, see the SCHEMABINDING section of [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2efef-158">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2efef-158">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-function"></a><span data-ttu-id="2efef-159">Per acquisire la definizione e le proprietà di una funzione</span><span class="sxs-lookup"><span data-stu-id="2efef-159">To get the definition and properties of a function</span></span>  
  
1.  <span data-ttu-id="2efef-160">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2efef-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2efef-161">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2efef-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2efef-162">Copiare e incollare uno degli esempi seguenti nella finestra della query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2efef-162">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the function name, definition, and relevant properties  
    SELECT sm.object_id,   
       OBJECT_NAME(sm.object_id) AS object_name,   
       o.type,   
       o.type_desc,   
       sm.definition,  
       sm.uses_ansi_nulls,  
       sm.uses_quoted_identifier,  
       sm.is_schema_bound,  
       sm.execute_as_principal_id  
    -- using the two system tables sys.sql_modules and sys.objects  
    FROM sys.sql_modules AS sm  
    JOIN sys.objects AS o ON sm.object_id = o.object_id  
    -- from the function 'dbo.ufnGetProductDealerPrice'  
    WHERE sm.object_id = OBJECT_ID('dbo.ufnGetProductDealerPrice')  
    ORDER BY o.type;  
    GO  
  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the definition of the function dbo.ufnGetProductDealerPrice  
    SELECT OBJECT_DEFINITION (OBJECT_ID('dbo.ufnGetProductDealerPrice')) AS ObjectDefinition;  
    GO  
    ```  
  
 <span data-ttu-id="2efef-163">Per altre informazioni, vedere [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) e [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2efef-163">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) and [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-function"></a><span data-ttu-id="2efef-164">Per acquisire le dipendenze di una funzione</span><span class="sxs-lookup"><span data-stu-id="2efef-164">To get the dependencies of a function</span></span>  
  
1.  <span data-ttu-id="2efef-165">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2efef-165">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2efef-166">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2efef-166">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2efef-167">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2efef-167">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get all of the dependency information  
    SELECT OBJECT_NAME(sed.referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(sed.referencing_id, sed.referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        sed.referencing_class_desc, sed.referenced_class_desc,  
        sed.referenced_server_name, sed.referenced_database_name, sed.referenced_schema_name,  
        sed.referenced_entity_name,   
        COALESCE(COL_NAME(sed.referenced_id, sed.referenced_minor_id), '(n/a)') AS referenced_column_name,  
        sed.is_caller_dependent, sed.is_ambiguous  
    -- from the two system tables sys.sql_expression_dependencies and sys.object  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    -- on the function dbo.ufnGetProductDealerPrice  
    WHERE sed.referencing_id = OBJECT_ID('dbo.ufnGetProductDealerPrice');  
    GO  
    ```  
  
 <span data-ttu-id="2efef-168">Per altre informazioni, vedere [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) e [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2efef-168">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
