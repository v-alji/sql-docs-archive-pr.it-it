---
title: MSSQLSERVER_2020 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2020 (Database Engine error)
ms.assetid: 4a8bf90f-a083-4c53-84f0-d23c711c8081
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5939267c37e90e7b8456dc01a4af79545e775656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636134"
---
# <a name="mssqlserver_2020"></a><span data-ttu-id="a964f-102">MSSQLSERVER_2020</span><span class="sxs-lookup"><span data-stu-id="a964f-102">MSSQLSERVER_2020</span></span>
    
## <a name="details"></a><span data-ttu-id="a964f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a964f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a964f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a964f-104">Product Name</span></span>|<span data-ttu-id="a964f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a964f-105">SQL Server</span></span>|  
|<span data-ttu-id="a964f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a964f-106">Event ID</span></span>|<span data-ttu-id="a964f-107">2020</span><span class="sxs-lookup"><span data-stu-id="a964f-107">2020</span></span>|  
|<span data-ttu-id="a964f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a964f-108">Event Source</span></span>|<span data-ttu-id="a964f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a964f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a964f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a964f-110">Component</span></span>|<span data-ttu-id="a964f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a964f-111">SQLEngine</span></span>|  
|<span data-ttu-id="a964f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a964f-112">Symbolic Name</span></span>||  
|<span data-ttu-id="a964f-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a964f-113">Message Text</span></span>|<span data-ttu-id="a964f-114">Le dipendenze segnalate per l'entità "%.\*ls" non includono riferimenti a colonne.</span><span class="sxs-lookup"><span data-stu-id="a964f-114">The dependencies reported for entity "%.\*ls" do not include references to columns.</span></span> <span data-ttu-id="a964f-115">L'entità fa riferimento a un oggetto che non esiste oppure si è verificato un errore in una o più istruzioni dell'entità.</span><span class="sxs-lookup"><span data-stu-id="a964f-115">This is either because the entity references an object that does not exist or because of an error in one or more statements in the entity.</span></span>  <span data-ttu-id="a964f-116">Prima di provare a eseguire nuovamente la query, accertarsi che non siano presenti errori nell'entità e che tutti gli oggetti a cui l'entità fa riferimento esistano.</span><span class="sxs-lookup"><span data-stu-id="a964f-116">Before rerunning the query, ensure that there are no errors in the entity and that all objects referenced by the entity exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a964f-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a964f-117">Explanation</span></span>  
 <span data-ttu-id="a964f-118">La funzione di sistema **sys.dm_sql_referenced_entities** segnalerà tutte le dipendenze a livello di colonna per i riferimenti associati a schema.</span><span class="sxs-lookup"><span data-stu-id="a964f-118">The **sys.dm_sql_referenced_entities** system function will report any column-level dependency for schema-bound references.</span></span> <span data-ttu-id="a964f-119">La funzione restituirà ad esempio tutte le dipendenze a livello di colonna per una vista indicizzata poiché una vista indicizzata richiede l'associazione allo schema.</span><span class="sxs-lookup"><span data-stu-id="a964f-119">For example, the function will report all column-level dependencies for an indexed view because an indexed view requires schema binding.</span></span> <span data-ttu-id="a964f-120">Tuttavia, quando l'entità a cui si fa riferimento non è associata a schema, le dipendenze della colonna vengono restituite solo quando è possibile associare tutte le istruzioni in cui si fa riferimento alle colonne.</span><span class="sxs-lookup"><span data-stu-id="a964f-120">However, when the referenced entity is not schema-bound, column dependencies are reported only when all statements in which the columns are referenced can be bound.</span></span> <span data-ttu-id="a964f-121">Le istruzioni possono essere associate correttamente solo se tutti gli oggetti esistono al momento dell'analisi delle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a964f-121">Statements can be successfully bound only if all objects exist at the time the statements are parsed.</span></span> <span data-ttu-id="a964f-122">Se un'istruzione definita nell'entità non viene associata, le dipendenze della colonna non verranno segnalate e la colonna **referenced_minor_id** restituirà 0.</span><span class="sxs-lookup"><span data-stu-id="a964f-122">If any statement defined in the entity fails to bind, column dependencies will not be reported and the **referenced_minor_id** column will return 0.</span></span> <span data-ttu-id="a964f-123">Quando le dipendenze della colonna non possono essere risolte, viene generato l'errore 2020.</span><span class="sxs-lookup"><span data-stu-id="a964f-123">When column dependencies cannot be resolved, error 2020 is raised.</span></span> <span data-ttu-id="a964f-124">Questo errore non impedisce alla query di restituire dipendenze a livello di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a964f-124">This error does not prevent the query from returning object-level dependencies.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a964f-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a964f-125">User Action</span></span>  
 <span data-ttu-id="a964f-126">Correggere tutti gli errori identificati nel messaggio prima dell'errore 2020.</span><span class="sxs-lookup"><span data-stu-id="a964f-126">Correct any errors identified in the message before error 2020.</span></span> <span data-ttu-id="a964f-127">Nell'esempio di codice seguente viene definita la vista `Production.ApprovedDocuments` nelle colonne `Title`, `ChangeNumber` e `Status` della tabella `Production.Document`.</span><span class="sxs-lookup"><span data-stu-id="a964f-127">For example, in the following code example the view `Production.ApprovedDocuments` is defined on the columns `Title`, `ChangeNumber`, and `Status` in the `Production.Document` table.</span></span> <span data-ttu-id="a964f-128">Viene eseguita una query sulla funzione di sistema **sys.dm_sql_referenced_entities** per gli oggetti e le colonne da cui dipende la vista `ApprovedDocuments`.</span><span class="sxs-lookup"><span data-stu-id="a964f-128">The **sys.dm_sql_referenced_entities** system function is queried for the objects and columns on which the `ApprovedDocuments` view depends.</span></span> <span data-ttu-id="a964f-129">Poiché la vista non viene creata utilizzando la clausola WITH SCHEMA_BINDING, è possibile modificare le colonne con riferimenti nella vista della tabella a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a964f-129">Because the view is not created using the WITH SCHEMA_BINDING clause, the columns referenced in the view can be modified in the referenced table.</span></span> <span data-ttu-id="a964f-130">Nell'esempio viene modificata la colonna `ChangeNumber` della tabella `Production.Document` rinominandola con `TrackingNumber`.</span><span class="sxs-lookup"><span data-stu-id="a964f-130">The example alters the column `ChangeNumber` in the `Production.Document` table by renaming it to `TrackingNumber`.</span></span> <span data-ttu-id="a964f-131">Viene eseguita di nuovo una query sulla vista del catalogo per la vista `ApprovedDocuments`. Non è però possibile eseguire l'associazione a tutte le colonne definite nella vista.</span><span class="sxs-lookup"><span data-stu-id="a964f-131">The catalog view is queried again for the `ApprovedDocuments` view; however it cannot bind to all the columns defined in the view.</span></span> <span data-ttu-id="a964f-132">Vengono restituiti gli errori 207 e 2020 identificando il problema.</span><span class="sxs-lookup"><span data-stu-id="a964f-132">Errors 207 and 2020 are returned identifying the problem.</span></span> <span data-ttu-id="a964f-133">Per risolvere il problema, è necessario modificare la vista in modo da riflettere il nuovo nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="a964f-133">To resolve the problem, the view must be altered to reflect the new name of the column.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `CREATE VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title, ChangeNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 `EXEC sp_rename 'Production.Document.ChangeNumber', 'TrackingNumber', 'COLUMN';`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 <span data-ttu-id="a964f-134">La query restituisce i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="a964f-134">The query returns the following error messages.</span></span>  
  
 `Msg 207, Level 16, State 1, Procedure ApprovedDocuments, Line 3`  
  
 `Invalid column name 'ChangeNumber'.`  
  
 `Msg 2020, Level 16, State 1, Line 1`  
  
 `The dependencies reported for entity`  
  
 `"Production.ApprovedDocuments" do not include references to`  
  
 `columns. This is either because the entity references an`  
  
 `object that does not exist or because of an error in one or`  
  
 `more statements in the entity. Before rerunning the query,`  
  
 `ensure that there are no errors in the entity and that all`  
  
 `objects referenced by the entity exist.`  
  
 <span data-ttu-id="a964f-135">Nell'esempio seguente viene corretto il nome della colonna nella vista.</span><span class="sxs-lookup"><span data-stu-id="a964f-135">The following example corrects the column name in the view.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `ALTER VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title,TrackingNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
## <a name="see-also"></a><span data-ttu-id="a964f-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a964f-136">See Also</span></span>  
 [<span data-ttu-id="a964f-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a964f-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
  
