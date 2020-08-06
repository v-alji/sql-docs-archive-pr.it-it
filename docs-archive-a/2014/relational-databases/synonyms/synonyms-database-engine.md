---
title: Sinonimi (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synonyms [SQL Server], about synonyms
ms.assetid: 6210e1d5-075f-47e4-ac8d-f84bcf26fbc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3494f4f5b13c422efb8e2a39597e131c10d81ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628583"
---
# <a name="synonyms-database-engine"></a><span data-ttu-id="0353c-102">Sinonimi (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="0353c-102">Synonyms (Database Engine)</span></span>
  <span data-ttu-id="0353c-103">Un sinonimo è un oggetto di database che viene utilizzato per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0353c-103">A synonym is a database object that serves the following purposes:</span></span>  
  
-   <span data-ttu-id="0353c-104">Fornisce un nome alternativo per un altro oggetto di database, definito oggetto di base, presente su un server locale o remoto.</span><span class="sxs-lookup"><span data-stu-id="0353c-104">Provides an alternative name for another database object, referred to as the base object, that can exist on a local or remote server.</span></span>  
  
-   <span data-ttu-id="0353c-105">Fornisce un livello di astrazione che consente di proteggere un'applicazione client dalle modifiche apportate al nome o alla posizione dell'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="0353c-105">Provides a layer of abstraction that protects a client application from changes made to the name or location of the base object.</span></span>  
  
 <span data-ttu-id="0353c-106">Si consideri ad esempio la tabella **Employee** di [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], che si trova su un server denominato **Server1**.</span><span class="sxs-lookup"><span data-stu-id="0353c-106">For example, consider the **Employee** table of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], located on a server named **Server1**.</span></span> <span data-ttu-id="0353c-107">Per farvi riferimento da un altro server, **Server2**, un'applicazione client dovrebbe usare il nome composto da quattro parti **Server1.AdventureWorks.Person.Employee**.</span><span class="sxs-lookup"><span data-stu-id="0353c-107">To reference this table from another server, **Server2**, a client application would have to use the four-part name **Server1.AdventureWorks.Person.Employee**.</span></span> <span data-ttu-id="0353c-108">Inoltre, se la tabella venisse spostata in un altro server, sarebbe necessario modificare l'applicazione client in modo da riflettere la modifica della posizione.</span><span class="sxs-lookup"><span data-stu-id="0353c-108">Also, if the location of the table were to change, for example, to another server, the client application would have to be modified to reflect that change.</span></span>  
  
 <span data-ttu-id="0353c-109">Per risolvere entrambi i problemi, è possibile creare un sinonimo, **EmpTable**, in **Server2** per la tabella **Employee** in **Server1**.</span><span class="sxs-lookup"><span data-stu-id="0353c-109">To address both these issues, you can create a synonym, **EmpTable**, on **Server2** for the **Employee** table on **Server1**.</span></span> <span data-ttu-id="0353c-110">L'applicazione client dovrà quindi usare unicamente il nome composto da una parte, **EmpTable**, per fare riferimento alla tabella **Employee** .</span><span class="sxs-lookup"><span data-stu-id="0353c-110">Now, the client application only has to use the single-part name, **EmpTable**, to reference the **Employee** table.</span></span> <span data-ttu-id="0353c-111">Se la posizione della tabella **Employee** viene modificata, sarà necessario modificare il sinonimo, **EmpTable**, per puntare alla nuova posizione della tabella **Employee** .</span><span class="sxs-lookup"><span data-stu-id="0353c-111">Also, if the location of the **Employee** table changes, you will have to modify the synonym, **EmpTable**, to point to the new location of the **Employee** table.</span></span> <span data-ttu-id="0353c-112">Poiché non esiste un'istruzione ALTER SYNONYM, è necessario prima eliminare il sinonimo, **EmpTable**, quindi ricrearlo con lo stesso nome, ma puntando alla nuova posizione della tabella **Employee**.</span><span class="sxs-lookup"><span data-stu-id="0353c-112">Because there is no ALTER SYNONYM statement, you first have to drop the synonym, **EmpTable**, and then re-create the synonym with the same name, but point the synonym to the new location of **Employee**.</span></span>  
  
 <span data-ttu-id="0353c-113">Un sinonimo appartiene a uno schema e, come gli altri oggetti di uno schema, deve avere un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="0353c-113">A synonym belongs to a schema, and like other objects in a schema, the name of a synonym must be unique.</span></span> <span data-ttu-id="0353c-114">È possibile creare sinonimi per gli oggetti di database seguenti:</span><span class="sxs-lookup"><span data-stu-id="0353c-114">You can create synonyms for the following database objects:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0353c-115">Stored procedure assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="0353c-115">Assembly (CLR) stored procedure</span></span>|<span data-ttu-id="0353c-116">Funzione con valori di tabella assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="0353c-116">Assembly (CLR) table-valued function</span></span>|  
|<span data-ttu-id="0353c-117">Funzione scalare assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="0353c-117">Assembly (CLR) scalar function</span></span>|<span data-ttu-id="0353c-118">Funzioni di aggregazione assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="0353c-118">Assembly (CLR) aggregate functions</span></span>|  
|<span data-ttu-id="0353c-119">Procedura di filtro della replica</span><span class="sxs-lookup"><span data-stu-id="0353c-119">Replication-filter-procedure</span></span>|<span data-ttu-id="0353c-120">Stored procedure estesa</span><span class="sxs-lookup"><span data-stu-id="0353c-120">Extended stored procedure</span></span>|  
|<span data-ttu-id="0353c-121">Funzione scalare SQL</span><span class="sxs-lookup"><span data-stu-id="0353c-121">SQL scalar function</span></span>|<span data-ttu-id="0353c-122">Funzione con valori di tabella SQL</span><span class="sxs-lookup"><span data-stu-id="0353c-122">SQL table-valued function</span></span>|  
|<span data-ttu-id="0353c-123">Funzione con valori di tabella inline SQL</span><span class="sxs-lookup"><span data-stu-id="0353c-123">SQL inline-tabled-valued function</span></span>|<span data-ttu-id="0353c-124">Stored procedure SQL</span><span class="sxs-lookup"><span data-stu-id="0353c-124">SQL stored procedure</span></span>|  
|<span data-ttu-id="0353c-125">Visualizza</span><span class="sxs-lookup"><span data-stu-id="0353c-125">View</span></span>|<span data-ttu-id="0353c-126">Tabella<sup>1</sup> (definita dall'utente)</span><span class="sxs-lookup"><span data-stu-id="0353c-126">Table<sup>1</sup> (User-defined)</span></span>|  
  
 <span data-ttu-id="0353c-127"><sup>1</sup> include tabelle temporanee locali e globali</span><span class="sxs-lookup"><span data-stu-id="0353c-127"><sup>1</sup> Includes local and global temporary tables</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0353c-128">I nomi composti da quattro parti non sono supportati per gli oggetti funzione di base.</span><span class="sxs-lookup"><span data-stu-id="0353c-128">Four-part names for function base objects are not supported.</span></span>  
  
 <span data-ttu-id="0353c-129">Un sinonimo non può essere l'oggetto di base di un altro sinonimo e non può fare riferimento a una funzione di aggregazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0353c-129">A synonym cannot be the base object for another synonym, and a synonym cannot reference a user-defined aggregate function.</span></span>  
  
 <span data-ttu-id="0353c-130">L'associazione tra un sinonimo e il relativo oggetto di base avviene unicamente in base al nome.</span><span class="sxs-lookup"><span data-stu-id="0353c-130">The binding between a synonym and its base object is by name only.</span></span> <span data-ttu-id="0353c-131">Tutti i controlli relativi all'esistenza, al tipo e alle autorizzazioni per l'oggetto di base sono rimandati alla fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0353c-131">All existence, type, and permissions checking on the base object is deferred until run time.</span></span> <span data-ttu-id="0353c-132">L'oggetto di base può pertanto essere modificato, eliminato o eliminato e sostituito da un altro oggetto con lo stesso nome dell'oggetto di base originale.</span><span class="sxs-lookup"><span data-stu-id="0353c-132">Therefore, the base object can be modified, dropped, or dropped and replaced by another object that has the same name as the original base object.</span></span> <span data-ttu-id="0353c-133">Si consideri ad esempio il sinonimo **MyContacts**che fa riferimento alla tabella **Person.Contact** di [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0353c-133">For example, consider a synonym, **MyContacts**, that references the **Person.Contact** table in [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span></span> <span data-ttu-id="0353c-134">Se la tabella **Contact** viene eliminata e sostituita da una vista denominata **Person.Contact**, il sinonimo **MyContacts** farà riferimento alla vista **Person.Contact** .</span><span class="sxs-lookup"><span data-stu-id="0353c-134">If the **Contact** table is dropped and replaced by a view named **Person.Contact**, **MyContacts** now references the **Person.Contact** view.</span></span>  
  
 <span data-ttu-id="0353c-135">I riferimenti a sinonimi non sono associati a schemi</span><span class="sxs-lookup"><span data-stu-id="0353c-135">References to synonyms are not schema-bound.</span></span> <span data-ttu-id="0353c-136">e pertanto è possibile eliminare un sinonimo in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="0353c-136">Therefore, a synonym can be dropped at any time.</span></span> <span data-ttu-id="0353c-137">Se si elimina un sinonimo, si corre tuttavia il rischio di lasciare riferimenti inesatti al sinonimo eliminato,</span><span class="sxs-lookup"><span data-stu-id="0353c-137">However, by dropping a synonym, you run the risk of leaving dangling references to the synonym that was dropped.</span></span> <span data-ttu-id="0353c-138">che verranno trovati solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0353c-138">These references will only be found at run time.</span></span>  
  
## <a name="synonyms-and-schemas"></a><span data-ttu-id="0353c-139">Sinonimi e schemi</span><span class="sxs-lookup"><span data-stu-id="0353c-139">Synonyms and Schemas</span></span>  
 <span data-ttu-id="0353c-140">Se è disponibile uno schema predefinito di cui non si è proprietari e si desidera creare un sinonimo, è necessario qualificare il nome del sinonimo con il nome dello schema di cui si è proprietari.</span><span class="sxs-lookup"><span data-stu-id="0353c-140">If you have a default schema that you do not own and want to create a synonym, you must qualify the synonym name with the name of a schema that you do own.</span></span> <span data-ttu-id="0353c-141">Se ad esempio si è proprietari di uno schema **x**, ma lo schema predefinito è **y** e si usa l'istruzione CREATE SYNONYM, è necessario anteporre al nome del sinonimo lo schema **x**, anziché assegnare al sinonimo un nome composto da una parte.</span><span class="sxs-lookup"><span data-stu-id="0353c-141">For example, if you own a schema **x**, but **y** is your default schema and you use the CREATE SYNONYM statement, you must prefix the name of the synonym with the schema **x**, instead of naming the synonym by using a single-part name.</span></span> <span data-ttu-id="0353c-142">Per altre informazioni sulla creazione dei sinonimi, vedere [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0353c-142">For more information about how to create synonyms, see [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span></span>  
  
## <a name="granting-permissions-on-a-synonym"></a><span data-ttu-id="0353c-143">Concessione delle autorizzazioni per un sinonimo</span><span class="sxs-lookup"><span data-stu-id="0353c-143">Granting Permissions on a Synonym</span></span>  
 <span data-ttu-id="0353c-144">Le autorizzazioni per un sinonimo possono essere concesse unicamente dai proprietari del sinonimo, membri di **db_owner**o di **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="0353c-144">Only synonym owners, members of **db_owner**, or members of **db_ddladmin** can grant permission on a synonym.</span></span>  
  
 <span data-ttu-id="0353c-145">È possibile concedere, negare o revocare le autorizzazioni seguenti per un sinonimo:</span><span class="sxs-lookup"><span data-stu-id="0353c-145">You can GRANT, DENY, REVOKE all or any of the following permissions on a synonym:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0353c-146">CONTROL</span><span class="sxs-lookup"><span data-stu-id="0353c-146">CONTROL</span></span>|<span data-ttu-id="0353c-147">DELETE</span><span class="sxs-lookup"><span data-stu-id="0353c-147">DELETE</span></span>|  
|<span data-ttu-id="0353c-148">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="0353c-148">EXECUTE</span></span>|<span data-ttu-id="0353c-149">INSERT</span><span class="sxs-lookup"><span data-stu-id="0353c-149">INSERT</span></span>|  
|<span data-ttu-id="0353c-150">SELECT</span><span class="sxs-lookup"><span data-stu-id="0353c-150">SELECT</span></span>|<span data-ttu-id="0353c-151">TAKE OWNERSHIP</span><span class="sxs-lookup"><span data-stu-id="0353c-151">TAKE OWNERSHIP</span></span>|  
|<span data-ttu-id="0353c-152">UPDATE</span><span class="sxs-lookup"><span data-stu-id="0353c-152">UPDATE</span></span>|<span data-ttu-id="0353c-153">VIEW DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0353c-153">VIEW DEFINITION</span></span>|  
  
## <a name="using-synonyms"></a><span data-ttu-id="0353c-154">Utilizzo dei sinonimi</span><span class="sxs-lookup"><span data-stu-id="0353c-154">Using Synonyms</span></span>  
 <span data-ttu-id="0353c-155">In diverse istruzioni SQL e contesti di espressione è possibile utilizzare sinonimi in sostituzione dell'oggetto di base a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="0353c-155">You can use synonyms in place of their referenced base object in several SQL statements and expression contexts.</span></span> <span data-ttu-id="0353c-156">Nella tabella seguente è riportato un elenco di tali istruzioni e contesti di espressione:</span><span class="sxs-lookup"><span data-stu-id="0353c-156">The following table contains a list of these statements and expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0353c-157">SELECT</span><span class="sxs-lookup"><span data-stu-id="0353c-157">SELECT</span></span>|<span data-ttu-id="0353c-158">INSERT</span><span class="sxs-lookup"><span data-stu-id="0353c-158">INSERT</span></span>|  
|<span data-ttu-id="0353c-159">UPDATE</span><span class="sxs-lookup"><span data-stu-id="0353c-159">UPDATE</span></span>|<span data-ttu-id="0353c-160">DELETE</span><span class="sxs-lookup"><span data-stu-id="0353c-160">DELETE</span></span>|  
|<span data-ttu-id="0353c-161">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="0353c-161">EXECUTE</span></span>|<span data-ttu-id="0353c-162">Sub-SELECT</span><span class="sxs-lookup"><span data-stu-id="0353c-162">Sub-selects</span></span>|  
  
 <span data-ttu-id="0353c-163">Quando si utilizzano i sinonimi nei contesti citati, l'istruzione viene eseguita sull'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="0353c-163">When you are working with synonyms in the contexts previously stated, the base object is affected.</span></span> <span data-ttu-id="0353c-164">Ad esempio, se un sinonimo fa riferimento a un oggetto di base che è una tabella e si inserisce una riga nel sinonimo, la riga verrà inserita nella tabella referenziata.</span><span class="sxs-lookup"><span data-stu-id="0353c-164">For example, if a synonym references a base object that is a table and you insert a row into the synonym, you are actually inserting a row into the referenced table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0353c-165">Non è possibile fare riferimento a un sinonimo che si trova in un server collegato.</span><span class="sxs-lookup"><span data-stu-id="0353c-165">You cannot reference a synonym that is located on a linked server.</span></span>  
  
 <span data-ttu-id="0353c-166">È possibile utilizzare un sinonimo come parametro per la funzione OBJECT_ID. Tuttavia, la funzione restituisce l'ID oggetto del sinonimo, anziché l'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="0353c-166">You can use a synonym as the parameter for the OBJECT_ID function; however, the function returns the object ID of the synonym, not the base object.</span></span>  
  
 <span data-ttu-id="0353c-167">Non è possibile fare riferimento a un sinonimo in un'istruzione DDL.</span><span class="sxs-lookup"><span data-stu-id="0353c-167">You cannot reference a synonym in a DDL statement.</span></span> <span data-ttu-id="0353c-168">Ad esempio, le istruzioni seguenti, che fanno riferimento a un sinonimo denominato `dbo.MyProduct`, generano errori:</span><span class="sxs-lookup"><span data-stu-id="0353c-168">For example, the following statements, which reference a synonym named `dbo.MyProduct`, generate errors:</span></span>  
  
```  
ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null;  
EXEC ('ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null');  
```  
  
 <span data-ttu-id="0353c-169">Le istruzioni di autorizzazione seguenti sono associate solo al sinonimo e non all'oggetto di base:</span><span class="sxs-lookup"><span data-stu-id="0353c-169">The following permission statements are associated only with the synonym and not the base object:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0353c-170">GRANT</span><span class="sxs-lookup"><span data-stu-id="0353c-170">GRANT</span></span>|<span data-ttu-id="0353c-171">NEGA</span><span class="sxs-lookup"><span data-stu-id="0353c-171">DENY</span></span>|  
|<span data-ttu-id="0353c-172">REVOKE</span><span class="sxs-lookup"><span data-stu-id="0353c-172">REVOKE</span></span>||  
  
 <span data-ttu-id="0353c-173">I sinonimi non sono associati a uno schema, pertanto non è possibile farvi riferimento con i seguenti contesti di espressione associati a schema:</span><span class="sxs-lookup"><span data-stu-id="0353c-173">Synonyms are not schema-bound and, therefore, cannot be referenced by the following schema-bound expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0353c-174">vincoli CHECK</span><span class="sxs-lookup"><span data-stu-id="0353c-174">CHECK constraints</span></span>|<span data-ttu-id="0353c-175">Colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="0353c-175">Computed columns</span></span>|  
|<span data-ttu-id="0353c-176">Espressioni predefinite</span><span class="sxs-lookup"><span data-stu-id="0353c-176">Default expressions</span></span>|<span data-ttu-id="0353c-177">Espressioni di regole</span><span class="sxs-lookup"><span data-stu-id="0353c-177">Rule expressions</span></span>|  
|<span data-ttu-id="0353c-178">Viste associate a schema</span><span class="sxs-lookup"><span data-stu-id="0353c-178">Schema-bound views</span></span>|<span data-ttu-id="0353c-179">Funzioni associate a schema</span><span class="sxs-lookup"><span data-stu-id="0353c-179">Schema-bound functions</span></span>|  
  
 <span data-ttu-id="0353c-180">Per altre informazioni sulle funzioni associate a schema, vedere [Creare funzioni definite dall'utente &#40;Motore di database&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="0353c-180">For more information about schema-bound functions, see [Create User-defined Functions &#40;Database Engine&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span></span>  
  
## <a name="getting-information-about-synonyms"></a><span data-ttu-id="0353c-181">Recupero di informazioni sui sinonimi</span><span class="sxs-lookup"><span data-stu-id="0353c-181">Getting Information About Synonyms</span></span>  
 <span data-ttu-id="0353c-182">La vista del catalogo sys.synonyms contiene una voce per ogni sinonimo incluso in un database specifico.</span><span class="sxs-lookup"><span data-stu-id="0353c-182">The sys.synonyms catalog view contains an entry for each synonym in a given database.</span></span> <span data-ttu-id="0353c-183">La vista del catalogo espone i metadati dei sinonimi, ad esempio il nome del sinonimo e il nome dell'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="0353c-183">This catalog view exposes synonym metadata such as the name of the synonym and the name of the base object.</span></span> <span data-ttu-id="0353c-184">Per ulteriori informazioni sulla `sys.synonyms` vista del catalogo, vedere [sys. sinonims &#40;&#41;Transact-SQL ](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0353c-184">For more information about the `sys.synonyms` catalog view, see [sys.synonyms &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span></span>  
  
 <span data-ttu-id="0353c-185">Utilizzando proprietà estese, è possibile aggiungere istruzioni o descrizioni, maschere di input e regole di formattazione come proprietà di un sinonimo.</span><span class="sxs-lookup"><span data-stu-id="0353c-185">By using extended properties, you can add descriptive or instructional text, input masks, and formatting rules as properties of a synonym.</span></span> <span data-ttu-id="0353c-186">Poiché la proprietà viene archiviata nel database, tutte le applicazioni che leggono la proprietà possono valutare l'oggetto nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="0353c-186">Because the property is stored in the database, all applications that read the property can evaluate the object in the same way.</span></span> <span data-ttu-id="0353c-187">Per altre informazioni, vedere [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0353c-187">For more information, see [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span></span>  
  
 <span data-ttu-id="0353c-188">Per trovare il tipo di base dell'oggetto di base di un sinonimo, utilizzare la funzione OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="0353c-188">To find the base type of the base object of a synonym, use the OBJECTPROPERTYEX function.</span></span> <span data-ttu-id="0353c-189">Per altre informazioni, vedere [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0353c-189">For more information, see [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0353c-190">Esempi</span><span class="sxs-lookup"><span data-stu-id="0353c-190">Examples</span></span>  
 <span data-ttu-id="0353c-191">Nell'esempio seguente viene restituito il tipo di base dell'oggetto di base di un sinonimo che rappresenta un oggetto locale.</span><span class="sxs-lookup"><span data-stu-id="0353c-191">The following example returns the base type of a synonym's base object that is a local object.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyEmployee   
FOR AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyEmployee'), 'BaseType') AS BaseType;  
```  
  
 <span data-ttu-id="0353c-192">Nell'esempio seguente viene restituito il tipo di base dell'oggetto di base di un sinonimo che rappresenta un oggetto remoto in un server denominato `Server1`.</span><span class="sxs-lookup"><span data-stu-id="0353c-192">The following example returns the base type of a synonym's base object that is a remote object located on a server named `Server1`.</span></span>  
  
```  
EXECUTE sp_addlinkedserver Server1;  
GO  
CREATE SYNONYM MyRemoteEmployee  
FOR Server1.AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyRemoteEmployee'), 'BaseType') AS BaseType;  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="0353c-193">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="0353c-193">Related Content</span></span>  
 [<span data-ttu-id="0353c-194">Creare sinonimi</span><span class="sxs-lookup"><span data-stu-id="0353c-194">Create Synonyms</span></span>](create-synonyms.md)  
  
 [<span data-ttu-id="0353c-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0353c-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
  
 [<span data-ttu-id="0353c-196">DROP SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0353c-196">DROP SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-synonym-transact-sql)  
  
  
