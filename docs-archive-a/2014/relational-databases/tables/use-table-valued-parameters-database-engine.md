---
title: Usare parametri con valori di tabella (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- DECLARE
- CREATE TYPE
helpviewer_keywords:
- table-valued parameters
- table-valued parameters, about table-valued parameters
- parameters [SQL Server], table-valued
- TVP See table-valued parameters
ms.assetid: 5e95a382-1e01-4c74-81f5-055612c2ad99
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa7013fddc6b2ce12ad9ad0f9fcb511d93915e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628567"
---
# <a name="use-table-valued-parameters-database-engine"></a><span data-ttu-id="374fd-102">Utilizzare parametri con valori di tabella (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="374fd-102">Use Table-Valued Parameters (Database Engine)</span></span>
  <span data-ttu-id="374fd-103">I parametri con valori di tabella vengono dichiarati utilizzando tipi di tabella definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="374fd-103">Table-valued parameters are declared by using user-defined table types.</span></span> <span data-ttu-id="374fd-104">I parametri con valori di tabella consentono di inviare più righe di dati a un'istruzione o a una routine [!INCLUDE[tsql](../../includes/tsql-md.md)] , ad esempio una stored procedure o una funzione, senza creare una tabella temporanea o molti parametri.</span><span class="sxs-lookup"><span data-stu-id="374fd-104">You can use table-valued parameters to send multiple rows of data to a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a routine, such as a stored procedure or function, without creating a temporary table or many parameters.</span></span>  
  
 <span data-ttu-id="374fd-105">I parametri con valori di tabella sono analoghi alle matrici di parametri in OLE DB e ODBC, ma offrono più flessibilità e maggiore integrazione con [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="374fd-105">Table-valued parameters are like parameter arrays in OLE DB and ODBC, but offer more flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="374fd-106">Un ulteriore vantaggio consiste nel fatto che tali parametri possono essere utilizzati in operazioni basate su set.</span><span class="sxs-lookup"><span data-stu-id="374fd-106">Table-valued parameters also have the benefit of being able to participate in set-based operations.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="374fd-107">passa i parametri con valori di tabella alle routine per riferimento in modo da evitare l'esecuzione di una copia dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="374fd-107">passes table-valued parameters to routines by reference to avoid making a copy of the input data.</span></span> <span data-ttu-id="374fd-108">È possibile creare ed eseguire routine [!INCLUDE[tsql](../../includes/tsql-md.md)] con parametri con valori di tabella e chiamarle da codice [!INCLUDE[tsql](../../includes/tsql-md.md)] o client gestiti o nativi in qualsiasi linguaggio gestito.</span><span class="sxs-lookup"><span data-stu-id="374fd-108">You can create and execute [!INCLUDE[tsql](../../includes/tsql-md.md)] routines with table-valued parameters, and call them from [!INCLUDE[tsql](../../includes/tsql-md.md)] code, managed and native clients in any managed language.</span></span>  
  
 <span data-ttu-id="374fd-109">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="374fd-109">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="374fd-110">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="374fd-110">Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="374fd-111">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="374fd-111">Restrictions</span></span>](#Restrictions)  
  
 [<span data-ttu-id="374fd-112">Parametri con valori di tabella  e operazioni BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="374fd-112">Table-Valued Parameters vs. BULK INSERT Operations</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="374fd-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="374fd-113">Example</span></span>](#Example)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="374fd-114">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="374fd-114">Benefits</span></span>  
 <span data-ttu-id="374fd-115">L'ambito di un parametro con valori di tabella è costituito dalla stored procedure, dalla funzione o dal testo [!INCLUDE[tsql](../../includes/tsql-md.md)] dinamico, esattamente come per gli altri parametri.</span><span class="sxs-lookup"><span data-stu-id="374fd-115">A table-valued parameter is scoped to the stored procedure, function, or dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] text, exactly like other parameters.</span></span> <span data-ttu-id="374fd-116">Analogamente, una variabile del tipo di tabella ha lo stesso ambito di qualsiasi altra variabile locale creata utilizzando un'istruzione DECLARE.</span><span class="sxs-lookup"><span data-stu-id="374fd-116">Similarly, a variable of table type has scope like any other local variable that is created by using a DECLARE statement.</span></span> <span data-ttu-id="374fd-117">È possibile dichiarare variabili con valori di tabella all'interno di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] dinamiche e passarle come parametri con valori di tabella a stored procedure e funzioni.</span><span class="sxs-lookup"><span data-stu-id="374fd-117">You can declare table-valued variables within dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and pass these variables as table-valued parameters to stored procedures and functions.</span></span>  
  
 <span data-ttu-id="374fd-118">I parametri con valori di tabella offrono maggiore flessibilità e, in alcuni casi, prestazioni migliori rispetto alle tabelle temporanee o ad altre modalità disponibili per passare un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="374fd-118">Table-valued parameters offer more flexibility and in some cases better performance than temporary tables or other ways to pass a list of parameters.</span></span> <span data-ttu-id="374fd-119">I parametri con valori di tabella offrono i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="374fd-119">Table-valued parameters offer the following benefits:</span></span>  
  
-   <span data-ttu-id="374fd-120">Non acquisiscono blocchi per il popolamento iniziale di dati da un client.</span><span class="sxs-lookup"><span data-stu-id="374fd-120">Do not acquire locks for the initial population of data from a client.</span></span>  
  
-   <span data-ttu-id="374fd-121">Forniscono un modello di programmazione semplice.</span><span class="sxs-lookup"><span data-stu-id="374fd-121">Provide a simple programming model.</span></span>  
  
-   <span data-ttu-id="374fd-122">Consentono di includere logica di business complessa in una singola routine.</span><span class="sxs-lookup"><span data-stu-id="374fd-122">Enable you to include complex business logic in a single routine.</span></span>  
  
-   <span data-ttu-id="374fd-123">Riducono il numero di round trip al server.</span><span class="sxs-lookup"><span data-stu-id="374fd-123">Reduce round trips to the server.</span></span>  
  
-   <span data-ttu-id="374fd-124">Possono avere una struttura di tabella con cardinalità diversa.</span><span class="sxs-lookup"><span data-stu-id="374fd-124">Can have a table structure of different cardinality.</span></span>  
  
-   <span data-ttu-id="374fd-125">Sono fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="374fd-125">Are strongly typed.</span></span>  
  
-   <span data-ttu-id="374fd-126">Consentono al client di specificare tipo di ordinamento e chiavi univoche.</span><span class="sxs-lookup"><span data-stu-id="374fd-126">Enable the client to specify sort order and unique keys.</span></span>  
  
-   <span data-ttu-id="374fd-127">Vengono memorizzati nella cache come una tabella temporanea quando vengono utilizzati in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="374fd-127">Are cached like a temp table when used in a stored procedure.</span></span> <span data-ttu-id="374fd-128">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], anche i parametri con valori di tabella sono memorizzati nella cache per le query con parametri.</span><span class="sxs-lookup"><span data-stu-id="374fd-128">Starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], table-valued parameters are also cached for parameterized queries.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="374fd-129">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="374fd-129">Restrictions</span></span>  
 <span data-ttu-id="374fd-130">Ai parametri con valori di tabella si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="374fd-130">Table-valued parameters have the following restrictions:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="374fd-131">non gestisce statistiche su colonne di parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="374fd-131">does not maintain statistics on columns of table-valued parameters.</span></span>  
  
-   <span data-ttu-id="374fd-132">I parametri con valori di tabella devono essere passati come parametri READONLY di input alle routine [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="374fd-132">Table-valued parameters must be passed as input READONLY parameters to [!INCLUDE[tsql](../../includes/tsql-md.md)] routines.</span></span> <span data-ttu-id="374fd-133">Non è possibile eseguire operazioni DML, ad esempio UPDATE, DELETE o INSERT, su un parametro con valori di tabella nel corpo di una routine.</span><span class="sxs-lookup"><span data-stu-id="374fd-133">You cannot perform DML operations such as UPDATE, DELETE, or INSERT on a table-valued parameter in the body of a routine.</span></span>  
  
-   <span data-ttu-id="374fd-134">Non è possibile utilizzare un parametro con valori di tabella come destinazione di un'istruzione SELECT INTO o INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="374fd-134">You cannot use a table-valued parameter as target of a SELECT INTO or INSERT EXEC statement.</span></span> <span data-ttu-id="374fd-135">Un parametro con valori di tabella può essere incluso nella clausola FROM di un'istruzione SELECT INTO o nella stringa o stored procedure INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="374fd-135">A table-valued parameter can be in the FROM clause of SELECT INTO or in the INSERT EXEC string or stored procedure.</span></span>  
  
##  <a name="table-valued-parameters-vs-bulk-insert-operations"></a><a name="BulkInsert"></a><span data-ttu-id="374fd-136">Confronto tra parametri con valori di tabella e operazioni BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="374fd-136">Table-Valued Parameters vs. BULK INSERT Operations</span></span>  
 <span data-ttu-id="374fd-137">L'utilizzo di parametri con valori di tabella è confrontabile con altre modalità di utilizzo di variabili basate su set, ma può spesso risultare più rapido nel caso di set di dati di notevoli dimensioni.</span><span class="sxs-lookup"><span data-stu-id="374fd-137">Using table-valued parameters is comparable to other ways of using set-based variables; however, using table-valued parameters frequently can be faster for large data sets.</span></span> <span data-ttu-id="374fd-138">Rispetto alle operazioni bulk, che comportano costi di avvio maggiori, i parametri con valori di tabella garantiscono livelli di prestazioni ottimali per operazioni di inserimento di non oltre 1.000 righe.</span><span class="sxs-lookup"><span data-stu-id="374fd-138">Compared to bulk operations that have a greater startup cost than table-valued parameters, table-valued parameters perform well for inserting less than 1000 rows.</span></span>  
  
 <span data-ttu-id="374fd-139">I parametri con valori di tabella riutilizzati possono sfruttare il vantaggio derivante dalla memorizzazione nella cache della tabella temporanea,</span><span class="sxs-lookup"><span data-stu-id="374fd-139">Table-valued parameters that are reused benefit from temporary table caching.</span></span> <span data-ttu-id="374fd-140">che consente di ottenere una migliore scalabilità rispetto alle operazioni BULK INSERT equivalenti.</span><span class="sxs-lookup"><span data-stu-id="374fd-140">This table caching enables better scalability than equivalent BULK INSERT operations.</span></span> <span data-ttu-id="374fd-141">Se si eseguono operazioni di inserimento di righe di entità ridotta, è possibile ottenere vantaggi minimi in termini di prestazioni utilizzando elenchi di parametri o istruzioni batch anziché operazioni BULK INSERT o parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="374fd-141">By using small row-insert operations a small performance benefit might be gained by using parameter lists or batched statements instead of BULK INSERT operations or table-valued parameters.</span></span> <span data-ttu-id="374fd-142">Tali metodi, tuttavia, risultano meno efficaci da programmare e le prestazioni si riducono rapidamente con l'aumentare del numero di righe.</span><span class="sxs-lookup"><span data-stu-id="374fd-142">However, these methods are less convenient to program, and performance decreases quickly as rows increase.</span></span>  
  
 <span data-ttu-id="374fd-143">I parametri con valori di tabella garantiscono livelli di prestazioni analoghi o migliori rispetto all'implementazione di una matrice di parametri equivalente.</span><span class="sxs-lookup"><span data-stu-id="374fd-143">Table-valued parameters perform equally well or better than an equivalent parameter array implementation.</span></span>  
  
##  <a name="example"></a><a name="Example"></a><span data-ttu-id="374fd-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="374fd-144">Example</span></span>  
 <span data-ttu-id="374fd-145">Nell'esempio seguente viene utilizzato [!INCLUDE[tsql](../../includes/tsql-md.md)] e viene illustrato come creare un tipo di parametro con valori di tabella, dichiarare una variabile per farvi riferimento, riempire un elenco di parametri e quindi passare i valori a una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="374fd-145">The following example uses [!INCLUDE[tsql](../../includes/tsql-md.md)] and shows you how to create a table-valued parameter type, declare a variable to reference it, fill the parameter list, and then pass the values to a stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
/* Create a table type. */  
CREATE TYPE LocationTableType AS TABLE   
( LocationName VARCHAR(50)  
, CostRate INT );  
GO  
  
/* Create a procedure to receive data for the table-valued parameter. */  
CREATE PROCEDURE dbo. usp_InsertProductionLocation  
    @TVP LocationTableType READONLY  
    AS   
    SET NOCOUNT ON  
    INSERT INTO AdventureWorks2012.Production.Location  
           (Name  
           ,CostRate  
           ,Availability  
           ,ModifiedDate)  
        SELECT *, 0, GETDATE()  
        FROM  @TVP;  
        GO  
  
/* Declare a variable that references the type. */  
DECLARE @LocationTVP AS LocationTableType;  
  
/* Add data to the table variable. */  
INSERT INTO @LocationTVP (LocationName, CostRate)  
    SELECT Name, 0.00  
    FROM AdventureWorks2012.Person.StateProvince;  
  
/* Pass the table variable data to a stored procedure. */  
EXEC usp_InsertProductionLocation @LocationTVP;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="374fd-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="374fd-146">See Also</span></span>  
 <span data-ttu-id="374fd-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="374fd-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span></span>  
 <span data-ttu-id="374fd-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="374fd-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="374fd-149">[sys. Types &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="374fd-149">[sys.types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span></span>  
 <span data-ttu-id="374fd-150">[sys. Parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="374fd-150">[sys.parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span></span>  
 <span data-ttu-id="374fd-151">[sys. parameter_type_usages &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="374fd-151">[sys.parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span></span>  
 <span data-ttu-id="374fd-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="374fd-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="374fd-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="374fd-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
