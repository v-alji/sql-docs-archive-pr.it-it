---
title: MSSQLSERVER_4104 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4104 (Database Engine error)
ms.assetid: 52dc32d8-97ad-4ef0-834d-2e68f215d007
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbbc28a3e15af6fdc8fd44633ccbdfc46e49149d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635642"
---
# <a name="mssqlserver_4104"></a><span data-ttu-id="c13ff-102">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="c13ff-102">MSSQLSERVER_4104</span></span>
    
## <a name="details"></a><span data-ttu-id="c13ff-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c13ff-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c13ff-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="c13ff-104">Product Name</span></span>|<span data-ttu-id="c13ff-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c13ff-105">SQL Server</span></span>|  
|<span data-ttu-id="c13ff-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="c13ff-106">Event ID</span></span>|<span data-ttu-id="c13ff-107">4104</span><span class="sxs-lookup"><span data-stu-id="c13ff-107">4104</span></span>|  
|<span data-ttu-id="c13ff-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="c13ff-108">Event Source</span></span>|<span data-ttu-id="c13ff-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c13ff-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c13ff-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c13ff-110">Component</span></span>|<span data-ttu-id="c13ff-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c13ff-111">SQLEngine</span></span>|  
|<span data-ttu-id="c13ff-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="c13ff-112">Symbolic Name</span></span>|<span data-ttu-id="c13ff-113">ALG_MULTI_ID_BAD</span><span class="sxs-lookup"><span data-stu-id="c13ff-113">ALG_MULTI_ID_BAD</span></span>|  
|<span data-ttu-id="c13ff-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="c13ff-114">Message Text</span></span>|<span data-ttu-id="c13ff-115">Impossibile associare l'identificatore in più parti "%. \* ls".</span><span class="sxs-lookup"><span data-stu-id="c13ff-115">The multi-part identifier "%.\*ls" could not be bound.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c13ff-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="c13ff-116">Explanation</span></span>  
 <span data-ttu-id="c13ff-117">Il nome di un'entità in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene definito *identificatore*.</span><span class="sxs-lookup"><span data-stu-id="c13ff-117">The name of an entity in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is referred to as its *identifier*.</span></span> <span data-ttu-id="c13ff-118">Gli identificatori vengono utilizzati quando si fa riferimento a entità, ad esempio, quando si specificano nomi di colonne e tabelle in una query.</span><span class="sxs-lookup"><span data-stu-id="c13ff-118">You use identifiers whenever you reference entities, for example, by specifying column and table names in a query.</span></span> <span data-ttu-id="c13ff-119">Un identificatore in più parti contiene uno o più qualificatori usati come prefisso.</span><span class="sxs-lookup"><span data-stu-id="c13ff-119">A multi-part identifier contains one or more qualifiers as a prefix for the identifier.</span></span> <span data-ttu-id="c13ff-120">Un identificatore di tabella può essere preceduto, ad esempio, da qualificatori come il nome del database e dello schema in cui è contenuta la tabella. Un identificatore di colonna può essere preceduto da qualificatori come un nome o un alias della tabella.</span><span class="sxs-lookup"><span data-stu-id="c13ff-120">For example, a table identifier may be prefixed with qualifiers such as the database name and schema name in which the table is contained, or a column identifier may be prefixed with qualifiers such as a table name or table alias.</span></span>  
  
 <span data-ttu-id="c13ff-121">L'errore 4104 indica che non è stato possibile eseguire il mapping dell'identificatore in più parti specificato a un'entità esistente.</span><span class="sxs-lookup"><span data-stu-id="c13ff-121">Error 4104 indicates that the specified multi-part identifier could not be mapped to an existing entity.</span></span> <span data-ttu-id="c13ff-122">Questo errore può essere restituito nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c13ff-122">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="c13ff-123">Il qualificatore fornito come prefisso per un nome di colonna non corrisponde ad alcun alias o nome di tabella utilizzato nella query.</span><span class="sxs-lookup"><span data-stu-id="c13ff-123">The qualifier supplied as a prefix for a column name does not correspond to any table or alias name used in the query.</span></span>  
  
     <span data-ttu-id="c13ff-124">Nell'istruzione seguente viene, ad esempio utilizzato un alias di tabella (`Dept`) come prefisso di colonna. Nella clausola FROM non viene tuttavia fatto riferimento a tale alias di tabella.</span><span class="sxs-lookup"><span data-stu-id="c13ff-124">For example, the following statement uses a table alias (`Dept`) as a column prefix, but the table alias is not referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department;  
    ```  
  
     <span data-ttu-id="c13ff-125">Nelle istruzioni seguenti un identificatore di colonna in più parti `TableB.KeyCol` viene specificato nella clausola WHERE come parte di una condizione JOIN tra due tabelle. A `TableB`, tuttavia, non viene fatto riferimento in modo esplicito nella query.</span><span class="sxs-lookup"><span data-stu-id="c13ff-125">In the following statements, a multi-part column identifier `TableB.KeyCol` is specified in the WHERE clause as part of a JOIN condition between two tables, however, `TableB` is not explicitly referenced in the query.</span></span>  
  
    ```  
    DELETE FROM TableA WHERE TableA.KeyCol = TableB.KeyCol;  
    ```  
  
    ```  
    SELECT 'X' FROM TableA WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="c13ff-126">Un nome di alias per la tabella viene specificato nella clausola FROM, ma il qualificatore fornito per una colonna è il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="c13ff-126">An alias name for the table is supplied in the FROM clause, but the qualifier supplied for a column is the table name.</span></span> <span data-ttu-id="c13ff-127">Nell'istruzione seguente, ad esempio, viene utilizzato il nome di tabella `Department` come prefisso di colonna. Nella clausola FROM è stato tuttavia specificato l'alias `Dept` per la tabella a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="c13ff-127">For example, the following statement uses the table name `Department` as the column prefix; however, the table has an alias (`Dept`) referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department AS Dept;  
    ```  
  
     <span data-ttu-id="c13ff-128">Quando viene utilizzato un alias, il nome della tabella non può essere utilizzato in altre posizioni all'interno dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c13ff-128">When an alias is used, the table name cannot be used elsewhere in the statement.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c13ff-129">non è in grado di determinare se l'identificatore in più parti fa riferimento a una colonna preceduta da una tabella o a una proprietà di un tipo di dati CLR definito dall'utente (UTD) preceduto da una colonna.</span><span class="sxs-lookup"><span data-stu-id="c13ff-129">is unable to determine if the multi-part identifier refers to a column prefixed by a table or to a property of a CLR user-defined data type (UDT) prefixed by a column.</span></span> <span data-ttu-id="c13ff-130">Ciò accade in quanto alle proprietà delle colonne definite dall'utente viene fatto riferimento utilizzando come separatore il punto (.) tra il nome della colonna e il nome della proprietà, così come un nome di colonna è preceduto da un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="c13ff-130">This happens because properties of UDT columns are referenced by using the period separator (.) between the column name and the property name in the same way that a column name is prefixed with a table name.</span></span> <span data-ttu-id="c13ff-131">Nell'esempio seguente vengono create due tabelle, ovvero `a` e `b`.</span><span class="sxs-lookup"><span data-stu-id="c13ff-131">The following example creates two tables, `a` and `b`.</span></span> <span data-ttu-id="c13ff-132">La tabella `b` contiene la colonna `a` che usa il tipo di dati CLR definito dall'utente `dbo.myudt2`.</span><span class="sxs-lookup"><span data-stu-id="c13ff-132">Table `b` contains column `a`, which uses a CLR UDT `dbo.myudt2` as its data type.</span></span> <span data-ttu-id="c13ff-133">L'istruzione SELECT contiene un identificatore in più parti `a.c2`.</span><span class="sxs-lookup"><span data-stu-id="c13ff-133">The SELECT statement contains a multi-part identifier `a.c2`.</span></span>  
  
    ```  
    CREATE TABLE a (c2 int);   
    GO  
    ```  
  
    ```  
    CREATE TABLE b (a dbo.myudt2);   
    GO  
    ```  
  
    ```  
    SELECT a.c2 FROM a, b;   
    ```  
  
     <span data-ttu-id="c13ff-134">Presupponendo che il tipo UDT `myudt2` non disponga di una proprietà denominata `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in grado di determinare se l'identificatore `a.c2` fa riferimento alla colonna `c2` nella tabella `a` o alla colonna `a`, proprietà `c2` nella tabella `b`.</span><span class="sxs-lookup"><span data-stu-id="c13ff-134">Assuming that the UDT `myudt2` does not have a property named `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot determine whether identifier `a.c2`refers to column `c2` in table `a` or to the column `a`, property `c2` in table `b`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c13ff-135">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c13ff-135">User Action</span></span>  
  
-   <span data-ttu-id="c13ff-136">Mettere in corrispondenza i prefissi di colonna con in nomi di tabella o gli alias specificati nella clausola FROM della query.</span><span class="sxs-lookup"><span data-stu-id="c13ff-136">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="c13ff-137">Se un alias è definito per un nome di tabella nella clausola FROM, è possibile utilizzare l'alias solo come qualificatore per le colonne associate alla tabella.</span><span class="sxs-lookup"><span data-stu-id="c13ff-137">If an alias is defined for a table name in the FROM clause, you can only use the alias as a qualifier for columns associated with that table.</span></span>  
  
     <span data-ttu-id="c13ff-138">Le istruzioni appena descritte che fanno riferimento alla tabella `HumanResources.Department` possono essere corrette nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c13ff-138">The statements above that reference the `HumanResources.Department` table can be corrected as follows:</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department AS Dept;  
    GO  
    ```  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department;  
    GO  
    ```  
  
-   <span data-ttu-id="c13ff-139">Assicurarsi che tutte le tabelle vengano specificate nella query e che le condizioni JOIN tra le tabelle vengano specificate correttamente.</span><span class="sxs-lookup"><span data-stu-id="c13ff-139">Ensure that all tables are specified in the query and that the JOIN conditions between tables are specified correctly.</span></span> <span data-ttu-id="c13ff-140">L'istruzione DELETE può essere corretta nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c13ff-140">The DELETE statement above can be corrected as follows:</span></span>  
  
    ```  
    DELETE FROM dbo.TableA  
    WHERE TableA.KeyCol = (SELECT TableB.KeyCol   
                            FROM TableB   
                            WHERE TableA.KeyCol = TableB.KeyCol);  
    GO  
    ```  
  
     <span data-ttu-id="c13ff-141">L'istruzione SELECT precedente relativa a `TableA` può essere corretta nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c13ff-141">The SELECT statement above for `TableA` can be corrected as follows:</span></span>  
  
    ```  
    SELECT 'X' FROM TableA, TableB WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
     <span data-ttu-id="c13ff-142">o</span><span class="sxs-lookup"><span data-stu-id="c13ff-142">or</span></span>  
  
    ```  
    SELECT 'X' FROM TableA INNER JOIN TableB ON TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="c13ff-143">Utilizzare nomi univoci chiaramente definiti per gli identificatori</span><span class="sxs-lookup"><span data-stu-id="c13ff-143">Use unique, clearly defined names for identifiers.</span></span> <span data-ttu-id="c13ff-144">per facilitare la lettura e la gestione del codice e ridurre inoltre il rischio di creare riferimenti ambigui a più entità.</span><span class="sxs-lookup"><span data-stu-id="c13ff-144">Doing so makes your code easier to read and maintain, and it also minimizes the risk of ambiguous references to multiple entities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13ff-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c13ff-145">See Also</span></span>  
 <span data-ttu-id="c13ff-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="c13ff-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span></span>  
 [<span data-ttu-id="c13ff-147">Identificatori del database</span><span class="sxs-lookup"><span data-stu-id="c13ff-147">Database Identifiers</span></span>](../databases/database-identifiers.md)  
  
  
