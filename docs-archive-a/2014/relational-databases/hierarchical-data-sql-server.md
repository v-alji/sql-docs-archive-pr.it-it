---
title: Dati gerarchici (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [SQL Server], tables to support
- hierarchyid [Database Engine], concepts
- hierarchical tables [Database Engine]
- SqlHierarchyId
- hierarchyid [Database Engine]
- hierarchical queries [SQL Server], using hierarchyid data type
ms.assetid: 19aefa9a-fbc2-4b22-92cf-67b8bb01671c
author: rothja
ms.author: jroth
ms.openlocfilehash: 351a5a4aa6bc1655b8da5fced3e51385dd498bdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627705"
---
# <a name="hierarchical-data-sql-server"></a><span data-ttu-id="f9eaa-102">Dati gerarchici [SQL Server]</span><span class="sxs-lookup"><span data-stu-id="f9eaa-102">Hierarchical Data (SQL Server)</span></span>
  <span data-ttu-id="f9eaa-103">Il `hierarchyid` tipo di dati incorporato rende più semplice archiviare ed eseguire query sui dati gerarchici.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-103">The built-in `hierarchyid` data type makes it easier to store and query hierarchical data.</span></span> <span data-ttu-id="f9eaa-104">`hierarchyid`è ottimizzato per la rappresentazione di alberi, che sono il tipo più comune di dati gerarchici.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-104">`hierarchyid` is optimized for representing trees, which are the most common type of hierarchical data.</span></span>  
  
 <span data-ttu-id="f9eaa-105">I dati gerarchici vengono definiti come un set di elementi di dati correlati tra loro tramite relazioni gerarchiche.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-105">Hierarchical data is defined as a set of data items that are related to each other by hierarchical relationships.</span></span> <span data-ttu-id="f9eaa-106">Si parla di relazioni gerarchiche quando un elemento di dati è l'elemento padre di un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-106">Hierarchical relationships exist where one item of data is the parent of another item.</span></span> <span data-ttu-id="f9eaa-107">Di seguito sono riportati alcuni esempi dei dati gerarchici comunemente archiviati nei database:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-107">Examples of the hierarchical data that is commonly stored in databases include the following:</span></span>  
  
-   <span data-ttu-id="f9eaa-108">Una struttura organizzativa</span><span class="sxs-lookup"><span data-stu-id="f9eaa-108">An organizational structure</span></span>  
  
-   <span data-ttu-id="f9eaa-109">Un file system</span><span class="sxs-lookup"><span data-stu-id="f9eaa-109">A file system</span></span>  
  
-   <span data-ttu-id="f9eaa-110">Un set di attività di un progetto</span><span class="sxs-lookup"><span data-stu-id="f9eaa-110">A set of tasks in a project</span></span>  
  
-   <span data-ttu-id="f9eaa-111">Una tassonomia di termini del linguaggio</span><span class="sxs-lookup"><span data-stu-id="f9eaa-111">A taxonomy of language terms</span></span>  
  
-   <span data-ttu-id="f9eaa-112">Un grafico di collegamenti tra pagine Web</span><span class="sxs-lookup"><span data-stu-id="f9eaa-112">A graph of links between Web pages</span></span>  
  
 <span data-ttu-id="f9eaa-113">Usare [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) come tipo di dati per creare tabelle con una struttura gerarchica o per descrivere la struttura gerarchica dei dati archiviati in un altro percorso.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) as a data type to create tables with a hierarchical structure, or to describe the hierarchical structure of data that is stored in another location.</span></span> <span data-ttu-id="f9eaa-114">Usare le [funzioni hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) di [!INCLUDE[tsql](../includes/tsql-md.md)] per eseguire query e gestire i dati gerarchici.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-114">Use the [hierarchyid functions](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) in [!INCLUDE[tsql](../includes/tsql-md.md)] to query and manage hierarchical data.</span></span>  
  
##  <a name="key-properties-of-hierarchyid"></a><a name="keyprops"></a> <span data-ttu-id="f9eaa-115">Proprietà chiave di hierarchyid</span><span class="sxs-lookup"><span data-stu-id="f9eaa-115">Key Properties of hierarchyid</span></span>  
 <span data-ttu-id="f9eaa-116">Un valore del tipo di dati `hierarchyid` rappresenta una posizione in un albero gerarchico.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-116">A value of the `hierarchyid` data type represents a position in a tree hierarchy.</span></span> <span data-ttu-id="f9eaa-117">I valori per `hierarchyid` hanno le proprietà descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-117">Values for `hierarchyid` have the following properties:</span></span>  
  
-   <span data-ttu-id="f9eaa-118">Estremamente compresso</span><span class="sxs-lookup"><span data-stu-id="f9eaa-118">Extremely compact</span></span>  
  
     <span data-ttu-id="f9eaa-119">Il numero medio di bit richiesto per rappresentare un nodo in un albero con *n* nodi dipende dal fanout medio, ovvero il numero medio di elementi figlio di un nodo.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-119">The average number of bits that are required to represent a node in a tree with *n* nodes depends on the average fanout (the average number of children of a node).</span></span> <span data-ttu-id="f9eaa-120">Per i fanout piccoli (0-7), la dimensione è approssimativamente 6\*logA*n* bit, dove A è il fanout medio.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-120">For small fanouts, (0-7) the size is about 6\*logA*n* bits, where A is the average fanout.</span></span> <span data-ttu-id="f9eaa-121">Un nodo in una gerarchia organizzativa di 100.000 persone con un fanout medio di 6 livelli richiede circa 38 bit.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-121">A node in an organizational hierarchy of 100,000 people with an average fanout of 6 levels takes about 38 bits.</span></span> <span data-ttu-id="f9eaa-122">Viene arrotondato a 40 bit, o 5 byte, per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-122">This is rounded up to 40 bits, or 5 bytes, for storage.</span></span>  
  
-   <span data-ttu-id="f9eaa-123">Il confronto avviene in ordine di scorrimento in profondità</span><span class="sxs-lookup"><span data-stu-id="f9eaa-123">Comparison is in depth-first order</span></span>  
  
     <span data-ttu-id="f9eaa-124">Dato due `hierarchyid` valori **a** e **b**, **un<b** indica che un oggetto precede b in un attraversamento del primo livello di profondità dell'albero.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-124">Given two `hierarchyid` values **a** and **b**, **a<b** means a comes before b in a depth-first traversal of the tree.</span></span> <span data-ttu-id="f9eaa-125">Gli indici sui tipi di dati `hierarchyid` sono in ordine di scorrimento della profondità e i nodi l'uno vicino all'altro nell'attraversamento del primo livello di profondità della struttura sono archiviati l'uno vicino all'altro.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-125">Indexes on `hierarchyid` data types are in depth-first order, and nodes close to each other in a depth-first traversal are stored near each other.</span></span> <span data-ttu-id="f9eaa-126">Ad esempio, i figli di un record sono archiviati adiacenti al record specifico.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-126">For example, the children of a record are stored adjacent to that record.</span></span>  
  
-   <span data-ttu-id="f9eaa-127">Supporto per eliminazioni e inserimenti arbitrari</span><span class="sxs-lookup"><span data-stu-id="f9eaa-127">Support for arbitrary insertions and deletions</span></span>  
  
     <span data-ttu-id="f9eaa-128">Usando il metodo [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) , è sempre possibile generare un elemento di pari livello a destra o a sinistra di un nodo oppure tra due elementi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-128">By using the [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) method, it is always possible to generate a sibling to the right of any given node, to the left of any given node, or between any two siblings.</span></span> <span data-ttu-id="f9eaa-129">La proprietà del confronto è gestita quando un numero arbitrario di nodi viene inserito o eliminato dalla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-129">The comparison property is maintained when an arbitrary number of nodes is inserted or deleted from the hierarchy.</span></span> <span data-ttu-id="f9eaa-130">La maggior parte degli inserimenti e delle eliminazioni mantiene la proprietà di compattezza.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-130">Most insertions and deletions preserve the compactness property.</span></span> <span data-ttu-id="f9eaa-131">Tuttavia, gli inserimenti tra due nodi produrranno i valori hierarchyid con una rappresentazione leggermente meno compatta.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-131">However, insertions between two nodes will produce hierarchyid values with a slightly less compact representation.</span></span>  
  
  
##  <a name="limitations-of-hierarchyid"></a><a name="limits"></a> <span data-ttu-id="f9eaa-132">Limitazioni di hierarchyid</span><span class="sxs-lookup"><span data-stu-id="f9eaa-132">Limitations of hierarchyid</span></span>  
 <span data-ttu-id="f9eaa-133">Il `hierarchyid` tipo di dati presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-133">The `hierarchyid` data type has the following limitations:</span></span>  
  
-   <span data-ttu-id="f9eaa-134">Una colonna di tipo `hierarchyid` non rappresenta automaticamente un albero.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-134">A column of type `hierarchyid` does not automatically represent a tree.</span></span> <span data-ttu-id="f9eaa-135">È compito dell'applicazione generare e assegnare i valori `hierarchyid` in maniera tale che la relazione desiderata tra le righe sia riflessa nei valori.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-135">It is up to the application to generate and assign `hierarchyid` values in such a way that the desired relationship between rows is reflected in the values.</span></span> <span data-ttu-id="f9eaa-136">In alcune applicazioni potrebbe essere presente una colonna di tipo `hierarchyid` in cui viene indicato il percorso in una gerarchia definita in un'altra tabella.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-136">Some applications might have a column of type `hierarchyid` that indicates the location in a hierarchy defined in another table.</span></span>  
  
-   <span data-ttu-id="f9eaa-137">La concorrenza nella generazione e nell'assegnazione dei valori `hierarchyid` deve essere gestita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-137">It is up to the application to manage concurrency in generating and assigning `hierarchyid` values.</span></span> <span data-ttu-id="f9eaa-138">Non c'è garanzia che i valori `hierarchyid` di una colonna siano univoci a meno che l'applicazione utilizzi un vincolo della chiave univoca o applichi univocità stessa tramite la logica.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-138">There is no guarantee that `hierarchyid` values in a column are unique unless the application uses a unique key constraint or enforces uniqueness itself through its own logic.</span></span>  
  
-   <span data-ttu-id="f9eaa-139">Le relazioni gerarchiche rappresentate dai valori `hierarchyid` non sono applicate come una relazione della chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-139">Hierarchical relationships represented by `hierarchyid` values are not enforced like a foreign key relationship.</span></span> <span data-ttu-id="f9eaa-140">È possibile e qualche volta appropriato avere una relazione gerarchica dove A ha un figlio B, A viene eliminato e lascia a B una relazione con un record inesistente.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-140">It is possible and sometimes appropriate to have a hierarchical relationship where A has a child B, and then A is deleted leaving B with a relationship to a nonexistent record.</span></span> <span data-ttu-id="f9eaa-141">Se questo comportamento è inaccettabile, tramite l'applicazione deve essere eseguita una query per i discendenti prima di eliminare gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-141">If this behavior is unacceptable, the application must query for descendants before deleting parents.</span></span>  
  
  
##  <a name="when-to-use-alternatives-to-hierarchyid"></a><a name="alternatives"></a> <span data-ttu-id="f9eaa-142">Quando utilizzare le alternative a hierarchyid</span><span class="sxs-lookup"><span data-stu-id="f9eaa-142">When to Use Alternatives to hierarchyid</span></span>  
 <span data-ttu-id="f9eaa-143">Di seguito sono riportate due alternative a `hierarchyid` per la rappresentazione di dati gerarchici:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-143">Two alternatives to `hierarchyid` for representing hierarchical data are:</span></span>  
  
-   <span data-ttu-id="f9eaa-144">Elemento padre/figlio</span><span class="sxs-lookup"><span data-stu-id="f9eaa-144">Parent/Child</span></span>  
  
-   <span data-ttu-id="f9eaa-145">XML</span><span class="sxs-lookup"><span data-stu-id="f9eaa-145">XML</span></span>  
  
 <span data-ttu-id="f9eaa-146">`hierarchyid` è generalmente superiore a queste alternative.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-146">`hierarchyid` is generally superior to these alternatives.</span></span> <span data-ttu-id="f9eaa-147">Tuttavia, esistono determinate situazioni illustrate in dettaglio di seguito in cui le alternative sono superiori.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-147">However, there are specific situations detailed below where the alternatives are likely superior.</span></span>  
  
### <a name="parentchild"></a><span data-ttu-id="f9eaa-148">Elemento padre/figlio</span><span class="sxs-lookup"><span data-stu-id="f9eaa-148">Parent/Child</span></span>  
 <span data-ttu-id="f9eaa-149">Quando si utilizza l'approccio dell'elemento padre/figlio, ogni riga contiene un riferimento all'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-149">When using the Parent/Child approach, each row contains a reference to the parent.</span></span> <span data-ttu-id="f9eaa-150">La tabella seguente definisce una tabella tipica utilizzata per contenere le righe padre e figlio in una relazione padre/figlio:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-150">The following table defines a typical table used to contain the parent and the child rows in a Parent/Child relationship:</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE TABLE ParentChildOrg  
   (  
    BusinessEntityID int PRIMARY KEY,  
    ManagerId int REFERENCES ParentChildOrg(BusinessEntityID),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
```  
  
 <span data-ttu-id="f9eaa-151">Confronto padre/figlio e `hierarchyid` per operazioni comuni</span><span class="sxs-lookup"><span data-stu-id="f9eaa-151">Comparing Parent/Child and `hierarchyid` for Common Operations</span></span>  
  
-   <span data-ttu-id="f9eaa-152">Le query del sottoalbero sono notevolmente più veloci con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-152">Subtree queries are significantly faster with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="f9eaa-153">Le query discendenti dirette sono leggermente più lente con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-153">Direct descendant queries are slightly slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="f9eaa-154">Lo spostamento di nodi non foglia è notevolmente più lento con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-154">Moving non-leaf nodes is slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="f9eaa-155">L'inserimento di nodi non foglia e l'inserimento o lo spostamento di nodi foglia sono caratterizzati dalla stessa complessità con `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-155">Inserting non-leaf nodes and inserting or moving leaf nodes has the same complexity with `hierarchyid`.</span></span>  
  
 <span data-ttu-id="f9eaa-156">La relazione elemento padre/figlio potrebbe essere superiore quando esistono le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-156">Parent/Child might be superior when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="f9eaa-157">La dimensione della chiave è importante.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-157">The size of the key is critical.</span></span> <span data-ttu-id="f9eaa-158">Per lo stesso numero di nodi, il valore `hierarchyid` è uguale a o maggiore di una famiglia di Integer (`smallint`, `int`, `bigint`).</span><span class="sxs-lookup"><span data-stu-id="f9eaa-158">For the same number of nodes, a `hierarchyid` value is equal to or larger than an integer-family (`smallint`, `int`, `bigint`) value.</span></span> <span data-ttu-id="f9eaa-159">Questo è solo uno dei motivi per cui utilizzare la relazione padre/figlio in casi rari, poiché `hierarchyid` si colloca meglio nell'I/O e nella complessità della CPU che nelle espressioni della tabella comune richieste quando si utilizza la struttura padre/figlio.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-159">This is only a reason to use Parent/Child in rare cases, because `hierarchyid` has significantly better locality of I/O and CPU complexity than the common table expressions required when you are using a Parent/Child structure.</span></span>  
  
-   <span data-ttu-id="f9eaa-160">Le query vengono eseguite raramente sulle sezioni della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-160">Queries rarely query across sections of the hierarchy.</span></span> <span data-ttu-id="f9eaa-161">In altre parole, le query di solito vengono eseguite solo su un singolo punto della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-161">In other words, queries usually address only a single point in the hierarchy.</span></span> <span data-ttu-id="f9eaa-162">In questi casi la condivisione percorso non è importante.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-162">In these cases co-location is not important.</span></span> <span data-ttu-id="f9eaa-163">Ad esempio, la relazione elemento padre/figlio è superiore se la tabella dell'organizzazione viene utilizzata solo per l'elaborazione del libro paga per i singoli dipendenti.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-163">For example, Parent/Child is superior when the organization table is only used to process payroll for individual employees.</span></span>  
  
-   <span data-ttu-id="f9eaa-164">I sottoalberi non-foglia vengono spostati frequentemente e le prestazioni sono molto importanti.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-164">Non-leaf subtrees move frequently and performance is very important.</span></span> <span data-ttu-id="f9eaa-165">In una rappresentazione padre/figlio, la modifica del percorso di una riga in una gerarchia influisce su una sola riga.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-165">In a parent/child representation changing the location of a row in a hierarchy affects a single row.</span></span> <span data-ttu-id="f9eaa-166">La modifica della posizione di una riga in un `hierarchyid` utilizzo influiscono su *n* righe, dove *n* è il numero di nodi nel sottoalbero spostato.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-166">Changing the location of a row in a `hierarchyid` usage affects *n* rows, where *n* is number of nodes in the sub-tree being moved.</span></span>  
  
     <span data-ttu-id="f9eaa-167">Se i sottoalberi non-foglia vengono spostati frequentemente e le prestazioni sono importanti, ma la maggior parte degli spostamenti è a un livello ben definito della gerarchia, suddividere i livelli superiori e inferiori in due gerarchie.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-167">If the non-leaf subtrees move frequently and performance is important, but most of the moves are at a well-defined level of the hierarchy, consider splitting the higher and lower levels into two hierarchies.</span></span> <span data-ttu-id="f9eaa-168">In questo modo, tutti gli spostamenti si verificano a livello di foglia nella gerarchia più elevata.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-168">This makes all moves into leaf-levels of the higher hierarchy.</span></span> <span data-ttu-id="f9eaa-169">Ad esempio, considerare una gerarchia di siti Web ospitata da un servizio.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-169">For instance, consider a hierarchy of Web sites hosted by a service.</span></span> <span data-ttu-id="f9eaa-170">I siti contengono molte pagine disposte in modo gerarchico.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-170">Sites contain many pages arranged in a hierarchical manner.</span></span> <span data-ttu-id="f9eaa-171">I siti ospitati potrebbero essere spostati in altri percorsi nella gerarchia del sito, tuttavia le pagine subordinate vengono raramente disposte in modo nuovo.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-171">Hosted sites might be moved to other locations in the site hierarchy, but the subordinate pages are rarely re-arranged.</span></span> <span data-ttu-id="f9eaa-172">Questo potrebbe essere rappresentato tramite:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-172">This could be represented via:</span></span>  
  
    ```  
    CREATE TABLE HostedSites   
       (  
        SiteId hierarchyid, PageId hierarchyid  
       ) ;  
    GO  
    ```  
  
  
### <a name="xml"></a><span data-ttu-id="f9eaa-173">XML</span><span class="sxs-lookup"><span data-stu-id="f9eaa-173">XML</span></span>  
 <span data-ttu-id="f9eaa-174">Un documento XML è un albero e pertanto una singola istanza del tipo di dati XML può rappresentare una gerarchia completa.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-174">An XML document is a tree, and therefore a single XML data type instance can represent a complete hierarchy.</span></span> <span data-ttu-id="f9eaa-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] quando viene creato un indice XML, `hierarchyid` i valori vengono usati internamente per rappresentare la posizione nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when an XML index is created, `hierarchyid` values are used internally to represent the position in the hierarchy.</span></span>  
  
 <span data-ttu-id="f9eaa-176">L'utilizzo del tipo di dati XML può essere superiore quando tutte le seguenti condizioni sono vere:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-176">Using XML data type can be superior when all the following are true:</span></span>  
  
-   <span data-ttu-id="f9eaa-177">La gerarchia completa viene sempre archiviata e recuperata.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-177">The complete hierarchy is always stored and retrieved.</span></span>  
  
-   <span data-ttu-id="f9eaa-178">I dati vengono utilizzati in un formato XML dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-178">The data is consumed in XML format by the application.</span></span>  
  
-   <span data-ttu-id="f9eaa-179">Le ricerche del predicato sono estremamente limitate e non sono importanti per la prestazione.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-179">Predicate searches are extremely limited and not performance critical.</span></span>  
  
 <span data-ttu-id="f9eaa-180">Ad esempio, se tramite un'applicazione vengono rilevate più organizzazioni, viene sempre archiviata e recuperata la gerarchia organizzativa completa e non viene eseguita alcuna query su una singola organizzazione, potrebbe essere utile una tabella con il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-180">For example, if an application tracks multiple organizations, always stores and retrieves the complete organizational hierarchy, and does not query into a single organization, a table of the following form might make sense:</span></span>  
  
```  
CREATE TABLE XMLOrg   
    (  
    Orgid int,  
    Orgdata xml  
    ) ;  
GO  
```  
  
  
##  <a name="indexing-strategies-for-hierarchical-data"></a><a name="indexing"></a> <span data-ttu-id="f9eaa-181">Strategie di indicizzazione per i dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="f9eaa-181">Indexing Strategies for Hierarchical Data</span></span>  
 <span data-ttu-id="f9eaa-182">Sono disponibili due strategie per indicizzare i dati gerarchici:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-182">There are two strategies for indexing hierarchical data:</span></span>  
  
-   <span data-ttu-id="f9eaa-183">**Depth-first**</span><span class="sxs-lookup"><span data-stu-id="f9eaa-183">**Depth-first**</span></span>  
  
     <span data-ttu-id="f9eaa-184">In un indice depth-first le righe di un sottoalbero vengono archiviate le une accanto alle altre.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-184">A depth-first index stores the rows in a subtree near each other.</span></span> <span data-ttu-id="f9eaa-185">Ad esempio, tutti i dipendenti che riportano a un responsabile vengono archiviati accanto al record dei responsabili.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-185">For example, all employees that report through a manager are stored near their managers' record.</span></span>  
  
     <span data-ttu-id="f9eaa-186">In un indice depth-first tutti i nodi del sottoalbero di un nodo vengono posizionati insieme.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-186">In a depth-first index, all nodes in the subtree of a node are co-located.</span></span> <span data-ttu-id="f9eaa-187">Gli indici depth-first sono pertanto utili per rispondere alle query sui sottoalberi, ad esempio "Trova tutti i file in questa cartella e nelle relative sottocartelle".</span><span class="sxs-lookup"><span data-stu-id="f9eaa-187">Depth-first indexes are therefore efficient for answering queries about subtrees, such as "Find all files in this folder and its subfolders".</span></span>  
  
-   <span data-ttu-id="f9eaa-188">**Breadth-first**</span><span class="sxs-lookup"><span data-stu-id="f9eaa-188">**Breadth-first**</span></span>  
  
     <span data-ttu-id="f9eaa-189">In un indice breadth-first le righe di ogni livello della gerarchia vengono archiviate insieme.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-189">A breadth-first stores the rows each level of the hierarchy together.</span></span> <span data-ttu-id="f9eaa-190">Ad esempio, i record dei dipendenti che riportano direttamente allo stesso responsabile vengono archiviati gli uni accanto agli altri.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-190">For example, the records of employees who directly report to the same manager are stored near each other.</span></span>  
  
     <span data-ttu-id="f9eaa-191">In un indice breadth-first tutti gli elementi figlio diretti di un nodo vengono posizionati insieme.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-191">In a breadth-first index all direct children of a node are co-located.</span></span> <span data-ttu-id="f9eaa-192">Pertanto, gli indici breadth-first sono in grado di fornire risposte alle query sugli elementi figlio immediati, ad esempio "Trova tutti i dipendenti che riportano direttamente a questo responsabile".</span><span class="sxs-lookup"><span data-stu-id="f9eaa-192">Breadth-first indexes are therefore efficient for answering queries about immediate children, such as "Find all employees who report directly to this manager".</span></span>  
  
 <span data-ttu-id="f9eaa-193">La scelta tra depth-first, breadth-first o entrambi e la selezione di uno di questi come chiave di clustering (se disponibile) dipendono dall'importanza relativa dei tipi di query riportati in precedenza e dall'importanza relativa delle operazioni SELECT e DML.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-193">Whether to have depth-first, breadth-first, or both, and which to make the clustering key (if any), depends on the relative importance of the above types of queries, and the relative importance of SELECT vs. DML operations.</span></span> <span data-ttu-id="f9eaa-194">Per un esempio dettagliato delle strategie di indicizzazione, vedere [Esercitazione: Utilizzo del tipo di dati hierarchyid](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f9eaa-194">For a detailed example of indexing strategies, see [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
### <a name="creating-indexes"></a><span data-ttu-id="f9eaa-195">Creazione di indici</span><span class="sxs-lookup"><span data-stu-id="f9eaa-195">Creating Indexes</span></span>  
 <span data-ttu-id="f9eaa-196">Il metodo GetLevel() può essere usato per creare un ordine breadth-first.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-196">The GetLevel() method can be used to create a breadth first ordering.</span></span> <span data-ttu-id="f9eaa-197">Nell'esempio seguente vengono creati sia gli indici breadth-first sia quelli depth-first:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-197">In the following example, both breadth-first and depth-first indexes are created:</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;   
GO  
  
CREATE TABLE Organization  
   (  
    BusinessEntityID hierarchyid,  
    OrgLevel as BusinessEntityID.GetLevel(),   
    EmployeeName nvarchar(50) NOT NULL  
   ) ;  
GO  
  
CREATE CLUSTERED INDEX Org_Breadth_First   
ON Organization(OrgLevel,BusinessEntityID) ;  
GO  
  
CREATE UNIQUE INDEX Org_Depth_First   
ON Organization(BusinessEntityID) ;  
GO  
```  
  
  
## <a name="examples"></a><span data-ttu-id="f9eaa-198">Esempi</span><span class="sxs-lookup"><span data-stu-id="f9eaa-198">Examples</span></span>  
  
### <a name="simple-example"></a><span data-ttu-id="f9eaa-199">Esempio semplice</span><span class="sxs-lookup"><span data-stu-id="f9eaa-199">Simple Example</span></span>  
 <span data-ttu-id="f9eaa-200">L'esempio seguente è intenzionalmente semplicistico per agevolare l'utilizzo iniziale.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-200">The following example is intentionally simplistic to help you get started.</span></span> <span data-ttu-id="f9eaa-201">Creare innanzitutto una tabella per contenere alcuni dati geography.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-201">First create a table to hold some geography data.</span></span>  
  
```  
CREATE TABLE SimpleDemo  
(Level hierarchyid NOT NULL,  
Location nvarchar(30) NOT NULL,  
LocationType nvarchar(9) NULL);  
```  
  
 <span data-ttu-id="f9eaa-202">A questo punto inserire i dati per alcuni continenti, paesi, stati e città.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-202">Now insert data for some continents, countries, states, and cities.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES   
('/1/', 'Europe', 'Continent'),  
('/2/', 'South America', 'Continent'),  
('/1/1/', 'France', 'Country'),  
('/1/1/1/', 'Paris', 'City'),  
('/1/2/1/', 'Madrid', 'City'),  
('/1/2/', 'Spain', 'Country'),  
('/3/', 'Antarctica', 'Continent'),  
('/2/1/', 'Brazil', 'Country'),  
('/2/1/1/', 'Brasilia', 'City'),  
('/2/1/2/', 'Bahia', 'State'),  
('/2/1/2/1/', 'Salvador', 'City'),  
('/3/1/', 'McMurdo Station', 'City');  
```  
  
 <span data-ttu-id="f9eaa-203">Selezionare i dati, aggiungendo una colonna in cui i dati del livello vengono convertiti in un valore di testo facile da capire.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-203">Select the data, adding a column that converts the Level data into a text value that is easy to understand.</span></span> <span data-ttu-id="f9eaa-204">Tramite questa query è inoltre possibile ordinare il risultato in base al tipo di dati `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-204">This query also orders the result by the `hierarchyid` data type.</span></span>  
  
```  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], *   
FROM SimpleDemo ORDER BY Level;  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
Converted Level  Level     Location         LocationType  
/1/              0x58      Europe           Continent  
/1/1/            0x5AC0    France           Country  
/1/1/1/          0x5AD6    Paris            City  
/1/2/            0x5B40    Spain            Country  
/1/2/1/          0x5B56    Madrid           City  
/2/              0x68      South America    Continent  
/2/1/            0x6AC0    Brazil           Country  
/2/1/1/          0x6AD6    Brasilia         City  
/2/1/2/          0x6ADA    Bahia            State  
/2/1/2/1/        0x6ADAB0  Salvador         City  
/3/              0x78      Antarctica       Continent  
/3/1/            0x7AC0    McMurdo Station  City  
```  
  
 <span data-ttu-id="f9eaa-205">Si noti che la gerarchia è una struttura valida, anche se non è coerente internamente.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-205">Notice that the hierarchy is has a valid structure, even though it is not internally consistent.</span></span> <span data-ttu-id="f9eaa-206">Bahia è l'unico stato.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-206">Bahia is the only state.</span></span> <span data-ttu-id="f9eaa-207">Viene visualizzato nella gerarchia come peer della città Brasilia.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-207">It appears in the hierarchy as a peer of the city Brasilia.</span></span> <span data-ttu-id="f9eaa-208">Analogamente, McMurdo Station non dispone di un paese padre.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-208">Similarly, McMurdo Station does not have a parent country.</span></span> <span data-ttu-id="f9eaa-209">Gli utenti dovranno decidere se questo tipo di gerarchia è appropriato per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-209">Users must decide if this type of hierarchy is appropriate for their use.</span></span>  
  
 <span data-ttu-id="f9eaa-210">Aggiungere un'altra riga e selezionare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-210">Add another row and select the results.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/1/3/1/', 'Kyoto', 'City'), ('/1/3/1/', 'London', 'City');  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], * FROM SimpleDemo ORDER BY Level;  
```  
  
 <span data-ttu-id="f9eaa-211">In questo modo vengono illustrati altri possibili problemi.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-211">This demonstrates more possible problems.</span></span> <span data-ttu-id="f9eaa-212">Kyoto può essere inserita come livello `/1/3/1/` anche se non esiste alcun livello padre `/1/3/`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-212">Kyoto can be inserted as level `/1/3/1/` even though there is no parent level `/1/3/`.</span></span> <span data-ttu-id="f9eaa-213">Inoltre, Londra e Kyoto presentano lo stesso valore per `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-213">And both London and Kyoto have the same value for the `hierarchyid`.</span></span> <span data-ttu-id="f9eaa-214">Anche in questo caso, gli utenti dovranno decidere se questo tipo di gerarchia è appropriato per l'utilizzo e bloccare i valori che non sono validi per lo scopo.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-214">Again, users must decide if this type of hierarchy is appropriate for their use, and block values that are invalid for their usage.</span></span>  
  
 <span data-ttu-id="f9eaa-215">Inoltre, in questa tabella non è stato utilizzato il primo livello della gerarchia `'/'`.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-215">Also, this table did not use the top of the hierarchy `'/'`.</span></span> <span data-ttu-id="f9eaa-216">È stato omesso perché non vi è alcun elemento padre comune per tutti i continenti.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-216">It was omitted because there is no common parent of all the continents.</span></span> <span data-ttu-id="f9eaa-217">È possibile inserirne uno aggiungendo l'intero pianeta.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-217">You can add one by adding the whole planet.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/', 'Earth', 'Planet');  
```  
  
##  <a name="related-tasks"></a><a name="tasks"></a> <span data-ttu-id="f9eaa-218">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="f9eaa-218">Related Tasks</span></span>  
  
###  <a name="migrating-from-parentchild-to-hierarchyid"></a><a name="migrating"></a> <span data-ttu-id="f9eaa-219">Migrazione dalla relazione elemento padre/figlio a hierarchyid</span><span class="sxs-lookup"><span data-stu-id="f9eaa-219">Migrating from Parent/Child to hierarchyid</span></span>  
 <span data-ttu-id="f9eaa-220">La maggior parte degli alberi viene rappresentata utilizzando la relazione elemento padre/figlio.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-220">Most trees are represented using Parent/Child.</span></span> <span data-ttu-id="f9eaa-221">Il modo più semplice per eseguire la migrazione da una struttura elemento padre/figlio a una tabella tramite `hierarchyid` consiste nell'utilizzare una colonna o una tabella temporanea per tenere traccia del numero di nodi a ogni livello della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-221">The easiest way to migrate from a Parent/Child structure to a table using `hierarchyid` is to use a temporary column or a temporary table to keep track of the number of nodes at each level of the hierarchy.</span></span> <span data-ttu-id="f9eaa-222">Per un esempio di migrazione di una tabella padre/figlio, vedere la lezione 1 di [Esercitazione: Utilizzo del tipo di dati hierarchyid](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f9eaa-222">For an example of migrating a Parent/Child table, see lesson 1 of [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
###  <a name="managing-a-tree-using-hierarchyid"></a><a name="BKMK_ManagingTrees"></a> <span data-ttu-id="f9eaa-223">Gestione di un albero tramite hierarchyid</span><span class="sxs-lookup"><span data-stu-id="f9eaa-223">Managing a Tree Using hierarchyid</span></span>  
 <span data-ttu-id="f9eaa-224">Tramite un'applicazione si può facilmente assicurare che una colonna `hierarchyid` rappresenti un albero, anche se ciò non accade necessariamente.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-224">Although a `hierarchyid` column does not necessarily represent a tree, an application can easily ensure that it does.</span></span>  
  
-   <span data-ttu-id="f9eaa-225">Durante la generazione di nuovi valori, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-225">When generating new values, do one of the following:</span></span>  
  
    -   <span data-ttu-id="f9eaa-226">Monitorare l'ultimo numero figlio nella riga padre.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-226">Keep track of the last child number in the parent row.</span></span>  
  
    -   <span data-ttu-id="f9eaa-227">Calcolare l'ultimo elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-227">Compute the last child.</span></span> <span data-ttu-id="f9eaa-228">Ciò richiede un indice breadth-first.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-228">Doing this efficiently requires a breadth-first index.</span></span>  
  
-   <span data-ttu-id="f9eaa-229">Applicare l'univocità creando un indice univoco sulla colonna, come parte di una chiave di clustering.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-229">Enforce uniqueness by creating a unique index on the column, perhaps as part of a clustering key.</span></span> <span data-ttu-id="f9eaa-230">Per garantire che vengano inseriti valori univoci, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-230">To ensure that unique values are inserted, do one of the following:</span></span>  
  
    -   <span data-ttu-id="f9eaa-231">Rilevare errori di violazione di chiave univoca e riprovare.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-231">Detect unique key violation failures and retry.</span></span>  
  
    -   <span data-ttu-id="f9eaa-232">Determinare l'univocità di ogni nuovo nodo figlio e inserirlo come parte di una transazione serializzabile.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-232">Determine the uniqueness of each new child node, and insert it as part of a serializable transaction.</span></span>  
  
  
#### <a name="example-using-error-detection"></a><span data-ttu-id="f9eaa-233">Esempio di utilizzo del rilevamento degli errori</span><span class="sxs-lookup"><span data-stu-id="f9eaa-233">Example Using Error Detection</span></span>  
 <span data-ttu-id="f9eaa-234">Nell'esempio seguente, il codice consente calcola il nuovo valore **EmployeeId** figlio, quindi rileva eventuali violazioni di chiave e torna al marcatore **INS_EMP** per ricalcolare il valore **EmployeeId** per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-234">In the following example, the sample code computes the new child **EmployeeId** value, and then detects any key violation and returns to **INS_EMP** marker to recompute the **EmployeeId** value for the new row:</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
CREATE TABLE Org_T1  
   (  
    EmployeeId hierarchyid PRIMARY KEY,  
    OrgLevel AS EmployeeId.GetLevel(),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
  
CREATE INDEX Org_BreadthFirst ON Org_T1(OrgLevel, EmployeeId)  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50) )   
AS  
BEGIN  
    DECLARE @last_child hierarchyid  
INS_EMP:   
    SELECT @last_child = MAX(EmployeeId) FROM Org_T1   
    WHERE EmployeeId.GetAncestor(1) = @mgrid  
INSERT Org_T1 (EmployeeId, EmployeeName)  
SELECT @mgrid.GetDescendant(@last_child, NULL), @EmpName   
-- On error, return to INS_EMP to recompute @last_child  
IF @@error <> 0 GOTO INS_EMP   
END ;  
GO  
```  
  
  
#### <a name="example-using-a-serializable-transaction"></a><span data-ttu-id="f9eaa-235">Esempio di utilizzo di una transazione serializzabile</span><span class="sxs-lookup"><span data-stu-id="f9eaa-235">Example Using a Serializable Transaction</span></span>  
 <span data-ttu-id="f9eaa-236">Al tipo di dati **Org_BreadthFirst** viene assicurato che per la determinazione di **@last_child** venga usata una ricerca di intervallo.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-236">The **Org_BreadthFirst** index ensures that determining **@last_child** uses a range seek.</span></span> <span data-ttu-id="f9eaa-237">Oltre ad altri casi di errore che un'applicazione potrebbe voler controllare, una violazione di chiave duplicata dopo l'inserimento indica un tentativo di aggiungere più dipendenti con lo stesso ID e pertanto **@last_child** deve essere ricalcolato.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-237">In addition to other error cases an application might want to check, a duplicate key violation after the insert indicates an attempt to add multiple employees with the same id, and therefore **@last_child** must be recomputed.</span></span> <span data-ttu-id="f9eaa-238">Nel codice seguente sono utilizzati una transazione serializzabile e un indice breadth-first per calcolare il valore del nodo nuovo:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-238">The following code uses a serializable transaction and a breadth-first index to compute the new node value:</span></span>  
  
```  
CREATE TABLE Org_T2  
    (  
    EmployeeId hierarchyid PRIMARY KEY,  
    LastChild hierarchyid,   
    EmployeeName nvarchar(50)   
    ) ;  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50))   
AS  
BEGIN  
DECLARE @last_child hierarchyid  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION   
  
UPDATE Org_T2   
SET @last_child = LastChild = EmployeeId.GetDescendant(LastChild,NULL)  
WHERE EmployeeId = @mgrid  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(@last_child, @EmpName)  
COMMIT  
END ;  
```  
  
 <span data-ttu-id="f9eaa-239">Tramite il codice seguente la tabella viene popolata con tre righe e vengono restituiti i risultati:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-239">The following code populates the table with three rows and returns the results:</span></span>  
  
```  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(hierarchyid::GetRoot(), 'David') ;  
GO  
AddEmp 0x , 'Sariya'  
GO  
AddEmp 0x58 , 'Mary'  
GO  
SELECT * FROM Org_T2  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
EmployeeId LastChild EmployeeName  
---------- --------- ------------  
0x        0x58       David  
0x58      0x5AC0     Sariya  
0x5AC0    NULL       Mary  
```  
  
  
###  <a name="enforcing-a-tree"></a><a name="BKMK_EnforcingTrees"></a> <span data-ttu-id="f9eaa-240">Applicazione di un albero</span><span class="sxs-lookup"><span data-stu-id="f9eaa-240">Enforcing a tree</span></span>  
 <span data-ttu-id="f9eaa-241">Negli esempi riportati in precedenza si illustra la possibilità di gestione di un albero da parte di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-241">The above examples illustrate how an application can ensure that a tree is maintained.</span></span> <span data-ttu-id="f9eaa-242">Per applicare un albero tramite vincoli, è possibile creare una colonna calcolata in cui viene definito l'elemento padre di ogni nodo con un vincolo di chiave esterna relativo all'ID della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-242">To enforce a tree by using constraints, a computed column that defines the parent of each node can be created with a foreign key constraint back to the primary key id.</span></span>  
  
```  
CREATE TABLE Org_T3  
(  
   EmployeeId hierarchyid PRIMARY KEY,  
   ParentId AS EmployeeId.GetAncestor(1) PERSISTED    
      REFERENCES Org_T3(EmployeeId),  
   LastChild hierarchyid,   
   EmployeeName nvarchar(50)  
)  
GO  
```  
  
 <span data-ttu-id="f9eaa-243">Questo metodo dell'applicazione di una relazione è preferito quando per il codice considerato non affidabile per la gestione dell'albero gerarchico è disponibile un accesso DML diretto alla tabella.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-243">This method of enforcing a relationship is preferred when code that is not trusted to maintain the hierarchical tree has direct DML access to the table.</span></span> <span data-ttu-id="f9eaa-244">Tuttavia, questo metodo potrebbe ridurre le prestazioni poiché è necessario controllare il vincolo in ogni operazione DML.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-244">However this method might reduce performance because the constraint must be checked on every DML operation.</span></span>  
  
  
###  <a name="finding-ancestors-by-using-the-clr"></a><a name="findclr"></a> <span data-ttu-id="f9eaa-245">Individuazione di predecessori tramite CLR</span><span class="sxs-lookup"><span data-stu-id="f9eaa-245">Finding Ancestors by Using the CLR</span></span>  
 <span data-ttu-id="f9eaa-246">Un'operazione comune che interessa due nodi in una gerarchia è la ricerca del predecessore comune minore.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-246">A common operation involving two nodes in a hierarchy is to find the lowest common ancestor.</span></span> <span data-ttu-id="f9eaa-247">Questo può essere scritto in [!INCLUDE[tsql](../includes/tsql-md.md)] o CLR, perché il `hierarchyid` tipo è disponibile in entrambi.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-247">This can be written in either [!INCLUDE[tsql](../includes/tsql-md.md)] or CLR, because the `hierarchyid` type is available in both.</span></span> <span data-ttu-id="f9eaa-248">Si consiglia di usare CLR poiché le prestazioni sono più rapide.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-248">CLR is recommended because performance will be faster.</span></span>  
  
 <span data-ttu-id="f9eaa-249">Utilizzare il codice CLR seguente per elencare i predecessori e cercare il predecessore comune minore:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-249">Use the following CLR code to list ancestors and to find the lowest common ancestor:</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Text;  
using Microsoft.SqlServer.Server;  
using Microsoft.SqlServer.Types;  
  
public partial class HierarchyId_Operations  
{  
    [SqlFunction(FillRowMethodName = "FillRow_ListAncestors")]  
    public static IEnumerable ListAncestors(SqlHierarchyId h)  
    {  
        while (!h.IsNull)  
        {  
            yield return (h);  
            h = h.GetAncestor(1);  
        }  
    }  
    public static void FillRow_ListAncestors(Object obj, out SqlHierarchyId ancestor)  
    {  
        ancestor = (SqlHierarchyId)obj;  
    }  
  
    public static HierarchyId CommonAncestor(SqlHierarchyId h1, HierarchyId h2)  
    {  
        while (!h1.IsDescendant(h2))  
            h1 = h1.GetAncestor(1);  
  
        return h1;  
    }  
}  
```  
  
 <span data-ttu-id="f9eaa-250">Per usare i metodi **ListAncestor** e **CommonAncestor** negli esempi [!INCLUDE[tsql](../includes/tsql-md.md)] seguenti, compilare la DLL e creare l'assembly **HierarchyId_Operations** in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] eseguendo un codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-250">To use the **ListAncestor** and **CommonAncestor** methods in the following [!INCLUDE[tsql](../includes/tsql-md.md)] examples, build the DLL and create the **HierarchyId_Operations** assembly in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by executing code similar to the following:</span></span>  
  
```  
CREATE ASSEMBLY HierarchyId_Operations   
FROM '<path to DLL>\ListAncestors.dll'  
GO  
```  
  
  
###  <a name="listing-ancestors"></a><a name="ancestors"></a> <span data-ttu-id="f9eaa-251">Elenco dei predecessori</span><span class="sxs-lookup"><span data-stu-id="f9eaa-251">Listing Ancestors</span></span>  
 <span data-ttu-id="f9eaa-252">La creazione di un elenco dei predecessori di un nodo è un'operazione comune che consente, ad esempio, di mostrare le posizioni di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-252">Creating a list of ancestors of a node is a common operation, for instance to show position in an organization.</span></span> <span data-ttu-id="f9eaa-253">A questo scopo, è possibile usare una funzione con valori di tabella tramite la classe **HierarchyId_Operations** definita in precedenza:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-253">One way of doing this is by using a table-valued-function using the **HierarchyId_Operations** class defined above:</span></span>  
  
 <span data-ttu-id="f9eaa-254">Utilizzo di [!INCLUDE[tsql](../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-254">Using [!INCLUDE[tsql](../includes/tsql-md.md)]:</span></span>  
  
```  
CREATE FUNCTION ListAncestors (@node hierarchyid)  
RETURNS TABLE (node hierarchyid)  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.ListAncestors  
GO  
```  
  
 <span data-ttu-id="f9eaa-255">Esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-255">Example of usage:</span></span>  
  
```  
DECLARE @h hierarchyid  
SELECT @h = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- /1/1/5/2/  
  
SELECT LoginID, OrgNode.ToString() AS LogicalNode  
FROM HumanResources.EmployeeDemo AS ED  
JOIN ListAncestors(@h) AS A   
   ON ED.OrgNode = A.Node  
GO  
```  
  
  
###  <a name="finding-the-lowest-common-ancestor"></a><a name="lowestcommon"></a> <span data-ttu-id="f9eaa-256">Ricerca del predecessore comune minore</span><span class="sxs-lookup"><span data-stu-id="f9eaa-256">Finding the Lowest Common Ancestor</span></span>  
 <span data-ttu-id="f9eaa-257">Usando la classe **HierarchyId_Operations** definita in precedenza, creare la funzione [!INCLUDE[tsql](../includes/tsql-md.md)] seguente per cercare il predecessore comune minore che interessa due nodi di una gerarchia:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-257">Using the **HierarchyId_Operations** class defined above, create the following [!INCLUDE[tsql](../includes/tsql-md.md)] function to find the lowest common ancestor involving two nodes in a hierarchy:</span></span>  
  
```  
CREATE FUNCTION CommonAncestor (@node1 hierarchyid, @node2 hierarchyid)  
RETURNS hierarchyid  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.CommonAncestor  
GO  
```  
  
 <span data-ttu-id="f9eaa-258">Esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="f9eaa-258">Example of usage:</span></span>  
  
```  
DECLARE @h1 hierarchyid, @h2 hierarchyid  
  
SELECT @h1 = OrgNode   
FROM  HumanResources.EmployeeDemo   
WHERE LoginID = 'adventure-works\jossef0' -- Node is /1/1/3/  
  
SELECT @h2 = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- Node is /1/1/5/2/  
  
SELECT OrgNode.ToString() AS LogicalNode, LoginID   
FROM HumanResources.EmployeeDemo    
WHERE OrgNode = dbo.CommonAncestor(@h1, @h2) ;  
```  
  
 <span data-ttu-id="f9eaa-259">Il nodo risultante è /1/1/</span><span class="sxs-lookup"><span data-stu-id="f9eaa-259">The resultant node is /1/1/</span></span>  
  
  
###  <a name="moving-subtrees"></a><a name="BKMK_MovingSubtrees"></a> <span data-ttu-id="f9eaa-260">Spostamento di sottoalberi</span><span class="sxs-lookup"><span data-stu-id="f9eaa-260">Moving Subtrees</span></span>  
 <span data-ttu-id="f9eaa-261">Un'altra operazione comune è lo spostamento di sottoalberi.</span><span class="sxs-lookup"><span data-stu-id="f9eaa-261">Another common operation is moving subtrees.</span></span> <span data-ttu-id="f9eaa-262">La procedura seguente prende il sottoalbero di **@oldMgr** e lo rende (incluso **@oldMgr** ) un sottoalbero di **@newMgr** .</span><span class="sxs-lookup"><span data-stu-id="f9eaa-262">The procedure below takes the subtree of **@oldMgr** and makes it (including **@oldMgr**) a subtree of **@newMgr**.</span></span>  
  
```  
CREATE PROCEDURE MoveOrg(@oldMgr nvarchar(256), @newMgr nvarchar(256) )  
AS  
BEGIN  
DECLARE @nold hierarchyid, @nnew hierarchyid  
SELECT @nold = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @oldMgr ;  
  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION  
SELECT @nnew = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @newMgr ;  
  
SELECT @nnew = @nnew.GetDescendant(max(OrgNode), NULL)   
FROM HumanResources.EmployeeDemo WHERE OrgNode.GetAncestor(1)=@nnew ;  
  
UPDATE HumanResources.EmployeeDemo    
SET OrgNode = OrgNode.GetReparentedValue(@nold, @nnew)  
WHERE OrgNode.IsDescendantOf(@nold) = 1 ;  
  
COMMIT TRANSACTION  
END ;  
GO  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="f9eaa-263">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9eaa-263">See Also</span></span>  
 <span data-ttu-id="f9eaa-264">[Guida di riferimento ai metodi per il tipo di dati hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="f9eaa-264">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="f9eaa-265">[Esercitazione: Utilizzo del tipo di dati hierarchyid](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="f9eaa-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span></span>  
 [<span data-ttu-id="f9eaa-266">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9eaa-266">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
