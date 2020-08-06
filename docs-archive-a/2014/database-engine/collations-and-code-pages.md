---
title: Regole di confronto e tabelle codici | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c626dcac-0474-432d-acc0-cfa643345372
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab904771fa8ac4acf25a624cbf3e1139f7e96434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630068"
---
# <a name="collations-and-code-pages"></a><span data-ttu-id="d2ee1-102">Tabelle codici e regole di confronto</span><span class="sxs-lookup"><span data-stu-id="d2ee1-102">Collations and Code Pages</span></span>
  <span data-ttu-id="d2ee1-103">In [!INCLUDE[hek_2](../includes/hek-2-md.md)] sono presenti restrizioni per le tabelle codici supportate per le colonne di tipo (var)char nelle tabelle ottimizzate per la memoria e nelle regole di confronto supportate utilizzate negli indici e nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-103">[!INCLUDE[hek_2](../includes/hek-2-md.md)] has restrictions on supported code pages for (var)char columns in memory-optimized tables and supported collations used in indexes and natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="d2ee1-104">La tabella codici per il valore (var)char determina il mapping tra i caratteri e la rappresentazione di byte archiviata nella tabella.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-104">The code page for a (var)char value determines the mapping between characters and the byte representation that is stored in the table.</span></span> <span data-ttu-id="d2ee1-105">Ad esempio, con la tabella codici Latin1 di Windows (1252, l'impostazione predefinita di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]), il carattere "a" corrisponde al byte 0x61.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-105">For example, with the Windows Latin 1 code page (1252; the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default), the character 'a' corresponds to the byte 0x61.</span></span>  
  
 <span data-ttu-id="d2ee1-106">La tabella codici di un valore (var)char viene determinata dalle regole di confronto associate al valore.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-106">The code page of a (var)char value is determined by the collation associated with the value.</span></span> <span data-ttu-id="d2ee1-107">Ad esempio, alle regole di confronto SQL_Latin1_General_CP1_CI_AS è associata la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-107">For example, the collation SQL_Latin1_General_CP1_CI_AS has the associated code page 1252.</span></span>  
  
 <span data-ttu-id="d2ee1-108">Le regole di confronto di un valore vengono ereditate dalle regole di confronto del database o possono essere specificate in modo esplicito utilizzando la parola chiave COLLATE.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-108">The collation of a value is either inherited from the database collation, or can be specified explicitly using the COLLATE keyword.</span></span> <span data-ttu-id="d2ee1-109">Le regole di confronto del database non possono essere modificate se il database contiene tabelle ottimizzate per la memoria o stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-109">Database collation cannot be changed if the database contains memory-optimized tables or natively compiled stored procedures.</span></span> <span data-ttu-id="d2ee1-110">Nell'esempio seguente vengono impostate le regole di confronto del database e viene creata una tabella che include una colonna con regole di confronto diverse.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-110">The following example sets the database collation and creates a table, which has a column with a different collation.</span></span> <span data-ttu-id="d2ee1-111">Nel database vengono utilizzate regole di confronto con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-111">The database uses Latin case-insensitive collation.</span></span>  
  
 <span data-ttu-id="d2ee1-112">Gli indici possono essere creati solo sulle colonne stringa se vengono utilizzate le regole di confronto BIN2.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-112">Indexes can only be created on string columns if they use a BIN2 collation.</span></span> <span data-ttu-id="d2ee1-113">Con la variabile LastName vengono utilizzate le regole di confronto BIN2.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-113">The LastName variable uses BIN2 collation.</span></span> <span data-ttu-id="d2ee1-114">FirstName utilizza il valore predefinito del database, ovvero CI_AS (senza distinzione tra maiuscole e minuscole, con distinzione tra caratteri accentati e non accentati).</span><span class="sxs-lookup"><span data-stu-id="d2ee1-114">FirstName uses the database default, which is CI_AS (case-insensitive, accent-sensitive).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d2ee1-115">Non è possibile utilizzare un filtro per ordinare o raggruppare gli elementi nelle colonne stringa dell'indice in cui non vengono applicate le regole di confronto BIN2.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-115">You cannot use order by or group by on index string columns that do not use BIN2 collation.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP  
  
ALTER DATABASE IMOLTP ADD FILEGROUP IMOLTP_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP ADD FILE( NAME = 'IMOLTP_mod' , FILENAME = 'c:\data\IMOLTP_mod') TO FILEGROUP IMOLTP_mod;  
--GO  
  
--  set the database collations  
ALTER DATABASE IMOLTP COLLATE Latin1_General_100_CI_AS  
GO  
  
--  
USE IMOLTP   
GO  
  
-- create a table with collation  
CREATE TABLE Employees (  
  EmployeeID int NOT NULL ,   
  LastName nvarchar(20) COLLATE Latin1_General_100_BIN2 NOT NULL INDEX IX_LastName NONCLUSTERED,   
  FirstName nvarchar(10) NOT NULL ,  
  CONSTRAINT PK_Employees PRIMARY KEY NONCLUSTERED HASH(EmployeeID)  WITH (BUCKET_COUNT=1024)  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_AND_DATA)  
GO  
```  
  
 <span data-ttu-id="d2ee1-116">Le restrizioni seguenti si applicano alle tabelle ottimizzate per la memoria e alle stored procedure compilate in modo nativo:</span><span class="sxs-lookup"><span data-stu-id="d2ee1-116">The following restrictions apply to memory-optimized tables and natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="d2ee1-117">Per le colonne di tipo (var)char in tabelle ottimizzate per la memoria è necessario utilizzare le regole di confronto della tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-117">(var)char columns in memory-optimized tables must use code page 1252 collation.</span></span> <span data-ttu-id="d2ee1-118">Questa restrizione non si applica alle colonne n(var)char.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-118">This restriction does not apply to n(var)char columns.</span></span> <span data-ttu-id="d2ee1-119">Il codice seguente recupera tutte le regole di confronto 1252:</span><span class="sxs-lookup"><span data-stu-id="d2ee1-119">The following code retrieves all 1252 collations:</span></span>  
  
    ```sql  
    -- all supported collations for (var)char columns in memory-optimized tables  
    select * from sys.fn_helpcollations()  
    where collationproperty(name, 'codepage') = 1252;  
    ```  
  
     <span data-ttu-id="d2ee1-120">Se è necessario archiviare caratteri non latini, utilizzare colonne di tipo colonne di tipo n(var)char.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-120">If you need to store non-Latin characters, use n(var)char columns.</span></span>  
  
-   <span data-ttu-id="d2ee1-121">Gli indici su colonne di tipo (n)(var)char possono essere specificati solo con le regole di confronto BIN2 (vedere il primo esempio).</span><span class="sxs-lookup"><span data-stu-id="d2ee1-121">Indexes on (n)(var)char columns can only be specified with BIN2 collations (see the first example).</span></span> <span data-ttu-id="d2ee1-122">La query seguente recupera tutte le regole di confronto BIN2 supportate:</span><span class="sxs-lookup"><span data-stu-id="d2ee1-122">The following query retrieves all supported BIN2 collations:</span></span>  
  
    ```sql  
    -- all supported collations for indexes on memory-optimized tables and   
    -- comparison/sorting in natively compiled stored procedures  
    select * from sys.fn_helpcollations() where name like '%BIN2'  
    ```  
  
     <span data-ttu-id="d2ee1-123">Se si accede alla tabella tramite codice [!INCLUDE[tsql](../includes/tsql-md.md)]interpretato, è possibile utilizzare la parola chiave `COLLATE` per modificare le regole di confronto con espressioni o operazioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-123">If you access the table through interpreted [!INCLUDE[tsql](../includes/tsql-md.md)], you can use the `COLLATE` keyword to change the collation with expressions or sort operations.</span></span> <span data-ttu-id="d2ee1-124">Vedere l'ultimo esempio a questo proposito.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-124">See the last example for a sample of this.</span></span>  
  
-   <span data-ttu-id="d2ee1-125">Le stored procedure compilate in modo non possono utilizzare parametri, variabili locali o costanti stringa di tipo (var)char se le regole di confronto del database non sono le regole di confronto della tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-125">Natively compiled stored procedures cannot use parameters, local variables, or string constants of (var)char type if the database collation is not a code page 1252 collation.</span></span>  
  
-   <span data-ttu-id="d2ee1-126">In tutte espressioni e le operazioni di ordinamento nelle stored procedure compilate in modo nativo devono essere utilizzate le regole di confronto BIN2.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-126">All expressions and sort operations inside natively compiled stored procedures must use BIN2 collations.</span></span> <span data-ttu-id="d2ee1-127">L'implicazione è che tutti i confronti e le operazioni di ordinamento si basano sugli elementi di codice Unicode dei caratteri (rappresentazioni binarie).</span><span class="sxs-lookup"><span data-stu-id="d2ee1-127">The implication is that all comparisons and sort operations are based on the Unicode code points of the characters (binary representations).</span></span> <span data-ttu-id="d2ee1-128">Ad esempio, in tutte le operazioni di ordinamento viene fatta distinzione tra maiuscole e minuscole (" Z" viene prima di "a ").</span><span class="sxs-lookup"><span data-stu-id="d2ee1-128">For example all sorting is case sensitive ('Z' comes before 'a').</span></span> <span data-ttu-id="d2ee1-129">Se necessario, utilizzare codice [!INCLUDE[tsql](../includes/tsql-md.md)] interpretato per le operazioni di ordinamento e confronto senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-129">If necessary, use interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] for case-insensitive sorting and comparison.</span></span>  
  
-   <span data-ttu-id="d2ee1-130">Il troncamento dei dati UTF-16 non è supportato nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-130">Truncation of UTF-16 data is not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="d2ee1-131">Ciò significa che i valori n (VAR) char (*n*) non possono essere convertiti nel tipo n (VAR) char (*i*) *, se i*  <  *n*, se le regole di confronto hanno _SC proprietà.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-131">This means that n(var)char(*n*) values cannot be converted to type n(var)char(*i*), if *i* < *n*, if the collation has _SC property.</span></span> <span data-ttu-id="d2ee1-132">Ad esempio, il codice seguente non è supportato:</span><span class="sxs-lookup"><span data-stu-id="d2ee1-132">For example, the following is not supported:</span></span>  
  
    ```sql  
    -- column definition using an _SC collation  
     c2 nvarchar(200) collate Latin1_General_100_CS_AS_SC not null   
    -- assignment to a smaller variable, requiring truncation  
     declare @c2 nvarchar(100) = '';  
     select @c2 = c2  
    ```  
  
     <span data-ttu-id="d2ee1-133">Le funzioni di modifica della stringa, ad esempio LEN, SUBSTRING, LTRIM e RTRIM con dati UTF-16 non sono supportate in stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-133">String manipulation functions, such as LEN, SUBSTRING, LTRIM, and RTRIM with UTF-16 data are not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="d2ee1-134">Non è possibile utilizzare queste funzioni per valori n(var)char con regole di confronto _SC.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-134">You cannot use these string manipulation functions for n(var)char values that have an _SC collation.</span></span>  
  
     <span data-ttu-id="d2ee1-135">Dichiarare le variabili utilizzando tipi sufficientemente grandi per evitare il troncamento.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-135">Declare variables using types that are large enough to avoid truncation.</span></span>  
  
 <span data-ttu-id="d2ee1-136">Nell'esempio seguente vengono illustrate alcune implicazioni e soluzioni alternative per le limitazioni delle regole di confronto in OLTP in memoria.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-136">The following example shows some of the implications and workarounds for the collation limitations in In-Memory OLTP.</span></span> <span data-ttu-id="d2ee1-137">Nell'esempio viene utilizzata la tabella Employees specificata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-137">The example uses the Employees table specified above.</span></span> <span data-ttu-id="d2ee1-138">Questo esempio elenca tutti i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-138">This sample list all employees .</span></span> <span data-ttu-id="d2ee1-139">Si noti che per LastName, a causa delle regole di confronto binarie, i nomi in maiuscolo vengono ordinati prima di quelli in minuscolo.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-139">Notice that for LastName, due to the binary collation, the upper case names are sorted before lower case.</span></span> <span data-ttu-id="d2ee1-140">Di conseguenza "Thomas" precede "nolan" perché i caratteri maiuscoli presentano elementi di codice più bassi.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-140">Therefore, 'Thomas' comes before 'nolan' because upper case characters have lower code points.</span></span> <span data-ttu-id="d2ee1-141">Per FirstName vengono utilizzate regole di confronto senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-141">FirstName has a case-insensitive collation.</span></span> <span data-ttu-id="d2ee1-142">L'ordinamento viene quindi applicato per lettera dell'alfabeto, non in base all'elemento di codice dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="d2ee1-142">So, sorting is by letter of the alphabet, not code point of the characters.</span></span>  
  
```sql  
-- insert a number of values  
INSERT Employees VALUES (1,'thomas', 'john')  
INSERT Employees VALUES (2,'Thomas', 'rupert')  
INSERT Employees VALUES (3,'Thomas', 'Jack')  
INSERT Employees VALUES (4,'Thomas', 'annie')  
INSERT Employees VALUES (5,'nolan', 'John')  
GO  
  
-- ===========  
SELECT EmployeeID, LastName, FirstName FROM Employees  
ORDER BY LastName, FirstName  
GO  
  
-- ===========  
-- specify collation: sorting uses case-insensitive collation, thus 'nolan' comes before 'Thomas'  
SELECT * FROM Employees  
ORDER BY LastName COLLATE Latin1_General_100_CI_AS, FirstName  
GO  
  
-- ===========  
-- retrieve employee by Name  
-- must use BIN2 collation for comparison in natively compiled stored procedures  
CREATE PROCEDURE usp_EmployeeByName @LastName nvarchar(20), @FirstName nvarchar(10)  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH   
(  TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
  LANGUAGE = N'us_english'  
)  
  SELECT EmployeeID, LastName, FirstName FROM dbo.Employees  
  WHERE   
    LastName = @LastName AND  
    FirstName COLLATE Latin1_General_100_BIN2 = @FirstName  
  
END  
GO  
  
-- this does not return any rows, as EmployeeID 1 has first name 'john', which is not equal to 'John' in a binary collation  
EXEC usp_EmployeeByName 'thomas', 'John'  
  
-- this retrieves EmployeeID 1  
EXEC usp_EmployeeByName 'thomas', 'john'  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2ee1-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2ee1-143">See Also</span></span>  
 [<span data-ttu-id="d2ee1-144">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="d2ee1-144">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
