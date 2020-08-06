---
title: Specificare le colonne calcolate in una tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, define
ms.assetid: 731a4576-09c1-47f0-a8f6-edd0b55679f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22e4df8d67b61e50383ffd8e33f982990ff3f2ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635966"
---
# <a name="specify-computed-columns-in-a-table"></a><span data-ttu-id="5a9a2-102">Specificare le colonne calcolate in una tabella</span><span class="sxs-lookup"><span data-stu-id="5a9a2-102">Specify Computed Columns in a Table</span></span>
  <span data-ttu-id="5a9a2-103">Una colonna calcolata è una colonna virtuale che non viene archiviata fisicamente nella tabella, a meno che non sia contrassegnata come PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-103">A computed column is a virtual column that is not physically stored in the table, unless the column is marked PERSISTED.</span></span> <span data-ttu-id="5a9a2-104">In un'espressione di colonna calcolata possono essere utilizzati dati di altre colonne per calcolare un valore per la colonna di appartenenza.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-104">A computed column expression can use data from other columns to calculate a value for the column to which it belongs.</span></span> <span data-ttu-id="5a9a2-105">È possibile specificare un'espressione per una colonna calcolata in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a9a2-105">You can specify an expression for a computed column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5a9a2-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5a9a2-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5a9a2-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5a9a2-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5a9a2-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5a9a2-108">Limitations and Restrictions</span></span>](#Limitations)  
  
     [<span data-ttu-id="5a9a2-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5a9a2-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5a9a2-110">**Per specificare una colonna calcolata:**</span><span class="sxs-lookup"><span data-stu-id="5a9a2-110">**To specify a computed column, using:**</span></span>  
  
     [<span data-ttu-id="5a9a2-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a9a2-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5a9a2-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a9a2-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a9a2-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5a9a2-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="5a9a2-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5a9a2-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5a9a2-115">Una colonna calcolata non può essere utilizzata come definizione di vincolo DEFAULT o FOREIGN KEY o con la definizione di vincolo NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-115">A computed column cannot be used as a DEFAULT or FOREIGN KEY constraint definition or with a NOT NULL constraint definition.</span></span> <span data-ttu-id="5a9a2-116">È tuttavia possibile utilizzare una colonna calcolata come colonna chiave di un indice o come parte di un vincolo PRIMARY KEY o UNIQUE, a condizione che il valore della colonna calcolata sia definito da un'espressione deterministica e il tipo di dati del risultato sia supportato nelle colonne dell'indice.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-116">However, if the computed column value is defined by a deterministic expression and the data type of the result is allowed in index columns, a computed column can be used as a key column in an index or as part of any PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="5a9a2-117">Se, ad esempio, la tabella contiene le colonne di tipo integer a e b, è possibile indicizzare la colonna calcolata a + b, ma non la colonna calcolata a+DATEPART(dd, GETDATE()), in quanto durante chiamate successive il valore potrebbe cambiare.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-117">For example, if the table has integer columns a and b, the computed column a + b may be indexed, but computed column a + DATEPART(dd, GETDATE()) cannot be indexed, because the value might change in subsequent invocations.</span></span>  
  
-   <span data-ttu-id="5a9a2-118">Non è possibile usare una colonna calcolata in un'istruzione INSERT o UPDATE.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-118">A computed column cannot be the target of an INSERT or UPDATE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5a9a2-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5a9a2-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5a9a2-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5a9a2-120">Permissions</span></span>  
 <span data-ttu-id="5a9a2-121">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5a9a2-122">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a9a2-122">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-add-a-new-computed-column"></a><a name="NewColumn"></a> <span data-ttu-id="5a9a2-123">Per aggiungere una nuova colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="5a9a2-123">To add a new computed column</span></span>  
  
1.  <span data-ttu-id="5a9a2-124">In **Esplora oggetti**espandere la tabella per cui si desidera aggiungere la nuova colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-124">In **Object Explorer**, expand the table for which you want to add the new computed column.</span></span> <span data-ttu-id="5a9a2-125">Fare clic con il pulsante destro del mouse su **Colonne** e scegliere **Nuova colonna**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-125">Right-click **Columns** and select **New Column**.</span></span>  
  
2.  <span data-ttu-id="5a9a2-126">Immettere il nome della colonna e accettare il tipo di dati predefinito (`nchar`(10)).</span><span class="sxs-lookup"><span data-stu-id="5a9a2-126">Enter the column name and accept the default data type (`nchar`(10)).</span></span> <span data-ttu-id="5a9a2-127">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] determina il tipo di dati della colonna calcolata applicando le regole sulla precedenza dei tipi di dati alle espressioni specificate nella formula.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-127">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines the data type of the computed column by applying the rules of data type precedence to the expressions specified in the formula.</span></span> <span data-ttu-id="5a9a2-128">Ad esempio, se la formula fa riferimento a una colonna di tipo `money` e una colonna di tipo `int`, la colonna calcolata sarà di tipo `money` perché tale tipo di dati ha precedenza maggiore.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-128">For example, if the formula references a column of type `money` and a column of type `int`, the computed column will be of type `money` because that data type has the higher precedence.</span></span> <span data-ttu-id="5a9a2-129">Per altre informazioni, vedere [Precedenza dei tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5a9a2-129">For more information, see [Data Type Precedence &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span></span>  
  
3.  <span data-ttu-id="5a9a2-130">Nella scheda **Proprietà colonne** espandere la proprietà **Specifica della colonna calcolata** .</span><span class="sxs-lookup"><span data-stu-id="5a9a2-130">In the **Column Properties** tab, expand the **Computed Column Specification** property.</span></span>  
  
4.  <span data-ttu-id="5a9a2-131">Nella proprietà figlio **(Formula)** immettere l'espressione per la colonna nella cella della griglia a destra.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-131">In the **(Formula)** child property, enter the expression for this column in the grid cell to the right.</span></span> <span data-ttu-id="5a9a2-132">Ad esempio, in una colonna `SalesTotal` , la formula immessa potrebbe essere `SubTotal+TaxAmt+Freight`, che aggiunge il valore in queste colonne per ogni riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-132">For example, in a `SalesTotal` column, the formula you enter might be `SubTotal+TaxAmt+Freight`, which adds the value in these columns for each row in the table.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5a9a2-133">Quando una formula combina due espressioni di tipi di dati diversi, le regole per la precedenza dei tipi di dati specificano che i tipi con precedenza inferiore vengano convertiti nei tipi con precedenza superiore.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-133">When a formula combines two expressions of different data types, the rules for data type precedence specify that the data type with the lower precedence is converted to the data type with the higher precedence.</span></span> <span data-ttu-id="5a9a2-134">Se la conversione non è una conversione implicita supportata, viene restituito l'errore`Error validating the formula for column column_name.`.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-134">If the conversion is not a supported implicit conversion, the error "`Error validating the formula for column column_name.`" is returned.</span></span> <span data-ttu-id="5a9a2-135">Utilizzare la funzione CAST o CONVERT per risolvere il conflitto del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-135">Use the CAST or CONVERT function to resolve the data type conflict.</span></span> <span data-ttu-id="5a9a2-136">Ad esempio, se una colonna di tipo `nvarchar` viene combinata con una colonna di tipo `int`, il tipo integer deve essere convertito in `nvarchar` come mostrato in questa formula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-136">For example, if a column of type `nvarchar` is combined with a column of type `int`, the integer type must be converted to `nvarchar` as shown in this formula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span></span> <span data-ttu-id="5a9a2-137">Per altre informazioni, vedere [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5a9a2-137">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
5.  <span data-ttu-id="5a9a2-138">Indicare se i dati sono persistenti selezionando **Sì** oppure **No** nell'elenco a discesa della proprietà figlio **Persistente** .</span><span class="sxs-lookup"><span data-stu-id="5a9a2-138">Indicate whether the data is persisted by choosing **Yes** or **No** from the drop-down for the **Is Persisted** child property.</span></span>  
  
6.  <span data-ttu-id="5a9a2-139">Nel menu **File** fare clic su **Salva**_nome tabella_.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-139">On the **File** menu, click **Save**_table name_.</span></span>  
  
#### <a name="to-add-a-computed-column-definition-to-an-existing-column"></a><span data-ttu-id="5a9a2-140">Per aggiungere una definizione di colonna calcolata a una colonna esistente</span><span class="sxs-lookup"><span data-stu-id="5a9a2-140">To add a computed column definition to an existing column</span></span>  
  
1.  <span data-ttu-id="5a9a2-141">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella con la colonna per cui si vuole modificare ed espandere la cartella **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="5a9a2-141">In **Object Explorer**, right-click the table with the column for which you want to change and expand the **Columns** folder.</span></span>  
  
2.  <span data-ttu-id="5a9a2-142">Fare clic con il pulsante destro del mouse sulla colonna per cui si vuole specificare una formula di colonna calcolata e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-142">Right-click the column for which you want to specify a computed column formula and click **Delete**.</span></span> <span data-ttu-id="5a9a2-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="5a9a2-144">Aggiungere una nuova colonna e specificare la formula della colonna calcolata attenendosi alla procedura precedente per aggiungere una nuova colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-144">Add a new column and specify the computed column formula by following the previous procedure to add a new computed column.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5a9a2-145">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a9a2-145">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-computed-column-when-creating-a-table"></a><span data-ttu-id="5a9a2-146">Per aggiungere una colonna calcolata quando si crea una tabella</span><span class="sxs-lookup"><span data-stu-id="5a9a2-146">To add a computed column when creating a table</span></span>  
  
1.  <span data-ttu-id="5a9a2-147">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a9a2-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5a9a2-148">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5a9a2-149">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-149">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="5a9a2-150">Nell'esempio viene creata una tabella con una colonna calcolata che moltiplica il valore della colonna `QtyAvailable` per il valore della colonna `UnitPrice` .</span><span class="sxs-lookup"><span data-stu-id="5a9a2-150">The example creates a table with a computed column that multiplies the value in the `QtyAvailable` column times the value in the `UnitPrice` column.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products   
    (  
        ProductID int IDENTITY (1,1) NOT NULL  
      , QtyAvailable smallint  
      , UnitPrice money  
      , InventoryValue AS QtyAvailable * UnitPrice  
    );  
  
    -- Insert values into the table.  
    INSERT INTO dbo.Products (QtyAvailable, UnitPrice)  
    VALUES (25, 2.00), (10, 1.5);  
  
    -- Display the rows in the table.  
    SELECT ProductID, QtyAvailable, UnitPrice, InventoryValue  
    FROM dbo.Products;  
  
    ```  
  
#### <a name="to-add-a-new-computed-column-to-an-existing-table"></a><span data-ttu-id="5a9a2-151">Per aggiungere una nuova colonna calcolata a una tabella esistente</span><span class="sxs-lookup"><span data-stu-id="5a9a2-151">To add a new computed column to an existing table</span></span>  
  
1.  <span data-ttu-id="5a9a2-152">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a9a2-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5a9a2-153">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5a9a2-154">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-154">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="5a9a2-155">Nell'esempio seguente viene aggiunta una nuova colonna alla tabella creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-155">The following example adds a new column to the table created in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.35);  
  
    ```  
  
#### <a name="to-change-an-existing-column-to-a-computed-column"></a><span data-ttu-id="5a9a2-156">Per impostare una colonna esistente su una colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="5a9a2-156">To change an existing column to a computed column</span></span>  
  
1.  <span data-ttu-id="5a9a2-157">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a9a2-157">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5a9a2-158">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5a9a2-159">Per modificare una colonna esistente in una colonna calcolata, rilasciare e ricreare la colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-159">To change an existing column to a computed column you must drop and re-create the computed column.</span></span> <span data-ttu-id="5a9a2-160">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-160">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="5a9a2-161">Nell'esempio seguente viene modificata la colonna aggiunta nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="5a9a2-161">The following example modifies the column added in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products DROP COLUMN RetailValue;  
    GO  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.5);  
  
    ```  
  
     <span data-ttu-id="5a9a2-162">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5a9a2-162">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
