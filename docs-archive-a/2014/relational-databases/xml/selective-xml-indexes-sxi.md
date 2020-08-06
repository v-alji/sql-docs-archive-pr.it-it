---
title: Indici XML selettivi (SXI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 598ecdcd-084b-4032-81b2-eed6ae9f5d44
author: rothja
ms.author: jroth
ms.openlocfilehash: 37dd72c5de2892672dc9f63066075ab5e770d758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637664"
---
# <a name="selective-xml-indexes-sxi"></a><span data-ttu-id="d00ef-102">Indici XML selettivi</span><span class="sxs-lookup"><span data-stu-id="d00ef-102">Selective XML Indexes (SXI)</span></span>
  <span data-ttu-id="d00ef-103">Gli indici XML selettivi rappresentano un altro tipo di indice XML disponibile oltre agli indici XML comuni.</span><span class="sxs-lookup"><span data-stu-id="d00ef-103">Selective XML indexes are another type of XML index that is available to you in addition to ordinary XML indexes.</span></span> <span data-ttu-id="d00ef-104">Di seguito sono indicati gli obiettivi della funzionalità degli indici XML selettivi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-104">The goals of the selective XML index feature are the following:</span></span>  
  
-   <span data-ttu-id="d00ef-105">Migliorare le prestazioni delle query sui dati XML archiviati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d00ef-105">To improve the performance of queries over XML data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="d00ef-106">Supportare un'indicizzazione più rapida di carichi di lavoro di dati XML di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d00ef-106">To support faster indexing of large XML data workloads.</span></span>  
  
-   <span data-ttu-id="d00ef-107">Migliorare la scalabilità riducendo i costi di archiviazione degli indici XML.</span><span class="sxs-lookup"><span data-stu-id="d00ef-107">To improve scalability by reducing the storage costs of XML indexes.</span></span>  
  
 <span data-ttu-id="d00ef-108">La limitazione principale negli indici XML più comuni è rappresentata dal fatto che viene eseguita l'indicizzazione dell'intero documento XML.</span><span class="sxs-lookup"><span data-stu-id="d00ef-108">The main limitation with ordinary XML indexes is that they index the entire XML document.</span></span> <span data-ttu-id="d00ef-109">Questa condizione determina significativi svantaggi, tra cui prestazioni ridotte per le query e costi di manutenzione dell'indice più elevati, in particolar modo per quanto riguarda i costi di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d00ef-109">This leads to several significant drawbacks, such as decreased query performance and increased index maintenance cost, mostly related to the storage costs of the index.</span></span>  
  
 <span data-ttu-id="d00ef-110">La funzionalità degli indici XML selettivi consente di promuovere solo determinati percorsi dai documenti XML da indicizzare.</span><span class="sxs-lookup"><span data-stu-id="d00ef-110">The selective XML index feature lets you promote only certain paths from the XML documents to index.</span></span> <span data-ttu-id="d00ef-111">In fase di creazione dell'indice, questi percorsi vengono sottoposti a valutazione e i nodi a cui puntano vengono suddivisi e archiviati in una tabella relazionale in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d00ef-111">At index creation time, these paths are evaluated, and the nodes that they point to are shredded and stored inside a relational table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d00ef-112">In questa funzionalità viene utilizzato un efficiente algoritmo di mapping sviluppato da [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research in collaborazione con il team di prodotto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d00ef-112">This feature uses an efficient mapping algorithm developed by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research in collaboration with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product team.</span></span> <span data-ttu-id="d00ef-113">Con questo algoritmo i nodi XML vengono mappati a una singola tabella relazionale, garantendo prestazioni eccezionali senza richiedere uno spazio di archiviazione di dimensioni eccessive.</span><span class="sxs-lookup"><span data-stu-id="d00ef-113">This algorithm maps the XML nodes to a single relational table, and achieves exceptional performance while requiring only modest storage space.</span></span>  
  
 <span data-ttu-id="d00ef-114">La funzionalità degli indici XML selettivi supporta inoltre indici XML selettivi secondari nei nodi indicizzati da un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-114">The selective XML index feature also supports secondary selective XML indexes over nodes that have been indexed by a selective XML index.</span></span> <span data-ttu-id="d00ef-115">Questi indici selettivi secondari risultano particolarmente efficaci e implicano un miglioramento delle prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="d00ef-115">These secondary selective indexes are efficient and further improve the performance of queries.</span></span>  
  
##  <a name="benefits-of-selective-xml-indexes"></a><a name="benefits"></a> <span data-ttu-id="d00ef-116">Vantaggi degli indici XML selettivi</span><span class="sxs-lookup"><span data-stu-id="d00ef-116">Benefits of Selective XML Indexes</span></span>  
 <span data-ttu-id="d00ef-117">Di seguito sono indicati i vantaggi offerti dagli indici XML selettivi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-117">Selective XML indexes provide the following benefits:</span></span>  
  
1.  <span data-ttu-id="d00ef-118">Prestazioni delle query notevolmente migliorate sul tipo di dati XML per carichi di query tipici.</span><span class="sxs-lookup"><span data-stu-id="d00ef-118">Greatly improved query performance over the XML data type for typical query loads.</span></span>  
  
2.  <span data-ttu-id="d00ef-119">Requisiti di archiviazione ridotti rispetto agli indici XML comuni.</span><span class="sxs-lookup"><span data-stu-id="d00ef-119">Reduced storage requirements compared to ordinary XML indexes.</span></span>  
  
3.  <span data-ttu-id="d00ef-120">Costi di manutenzione dell'indice ridotti rispetto agli indici XML comuni.</span><span class="sxs-lookup"><span data-stu-id="d00ef-120">Reduced index maintenance costs compared to ordinary XML indexes.</span></span>  
  
4.  <span data-ttu-id="d00ef-121">Nessuna necessità di aggiornare le applicazioni per ricavare vantaggi dagli indici XML selettivi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-121">No need to update applications to benefit from selective XML indexes.</span></span>  
  

  
##  <a name="selective-xml-indexes-and-primary-xml-indexes"></a><a name="compare"></a> <span data-ttu-id="d00ef-122">Indici XML selettivi e indici XML primari</span><span class="sxs-lookup"><span data-stu-id="d00ef-122">Selective XML Indexes and Primary XML Indexes</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d00ef-123">Creare un indice XML selettivo anziché un indice XML comune nella maggior parte dei casi per migliorare le prestazioni e usufruire di uno spazio di archiviazione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="d00ef-123">Create a selective XML index instead of an ordinary XML index in most cases for better performance and more efficient storage.</span></span>  
  
 <span data-ttu-id="d00ef-124">Non è tuttavia consigliabile creare un indice XML selettivo in presenza di una delle condizioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="d00ef-124">However, a selective XML index is not recommended when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="d00ef-125">Viene eseguito il mapping di un numero elevato di percorsi del nodo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-125">You map a large number of node paths.</span></span>  
  
-   <span data-ttu-id="d00ef-126">Vengono supportate le query per elementi sconosciuti o in una posizione sconosciuta nella struttura del documento.</span><span class="sxs-lookup"><span data-stu-id="d00ef-126">You support queries for unknown elements or elements in an unknown location in the document structure.</span></span>  
  

  
##  <a name="simple-example-of-a-selective-xml-index"></a><a name="example"></a> <span data-ttu-id="d00ef-127">Semplice esempio di un indice XML selettivo</span><span class="sxs-lookup"><span data-stu-id="d00ef-127">Simple Example of a Selective XML Index</span></span>  
 <span data-ttu-id="d00ef-128">Considerare il frammento XML indicato di seguito come un documento XML in una tabella di circa 500.000 righe:</span><span class="sxs-lookup"><span data-stu-id="d00ef-128">Consider the following XML fragment as an XML document in a table of approximately 500,000 rows:</span></span>  
  
```xml  
<book>  
    <created>2004-03-01</created>   
    <authors>Various</authors>  
    <subjects>  
        <subject>English wit and humor -- Periodicals</subject>  
        <subject>AP</subject>   
    </subjects>  
    <title>Punch, or the London Charivari, Volume 156, April 2, 1919</title>  
    <id>etext11617</id>  
</book>  
```  
  
 <span data-ttu-id="d00ef-129">Creare un indice XML primario per un numero così elevato di righe in questo semplice schema richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-129">Creating a primary XML index over so many rows of this simple schema takes a long time.</span></span> <span data-ttu-id="d00ef-130">L'esecuzione di query su questi dati risente inoltre del fatto che un indice XML primario non supporta l'indicizzazione selettiva.</span><span class="sxs-lookup"><span data-stu-id="d00ef-130">Querying this data also suffers from the fact that a primary XML index does not support selective indexing.</span></span>  
  
 <span data-ttu-id="d00ef-131">Se è necessario esclusivamente eseguire una query su questi dati per il percorso `/book/title` e il percorso `/book/subjects` , è possibile creare l'indice XML selettivo seguente:</span><span class="sxs-lookup"><span data-stu-id="d00ef-131">If you only need to query this data over the `/book/title` path and the `/book/subjects` path, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX SXI_index  
ON Tbl(xmlcol)  
FOR   
(  
    pathTitle = '/book/title/text()' AS XQUERY 'xs:string',   
    pathAuthors = '/book/authors' AS XQUERY 'node()',  
    pathId = '/book/id' AS SQL NVARCHAR(100)  
)  
```  
  
 <span data-ttu-id="d00ef-132">L'istruzione precedente rappresenta un esempio calzante della sintassi CREATE utilizzata per la creazione di un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-132">The preceding statement is a good example of the CREATE syntax that you use when you create a selective XML index.</span></span> <span data-ttu-id="d00ef-133">Nell'istruzione CREATE è necessario in primo luogo fornire un nome per l'indice e identificare la tabella e la colonna XML da indicizzare.</span><span class="sxs-lookup"><span data-stu-id="d00ef-133">In the CREATE statement, first you provide a name for the index and identify the table and the XML column to index.</span></span> <span data-ttu-id="d00ef-134">È quindi necessario specificare i percorsi per l'indice.</span><span class="sxs-lookup"><span data-stu-id="d00ef-134">Then you provide the paths to index.</span></span> <span data-ttu-id="d00ef-135">Un percorso include tre parti:</span><span class="sxs-lookup"><span data-stu-id="d00ef-135">A path has three parts:</span></span>  
  
1.  <span data-ttu-id="d00ef-136">Un nome che identifica in modo univoco il percorso.</span><span class="sxs-lookup"><span data-stu-id="d00ef-136">A name that uniquely identifies the path.</span></span>  
  
2.  <span data-ttu-id="d00ef-137">Un'espressione XQuery che descrive il percorso.</span><span class="sxs-lookup"><span data-stu-id="d00ef-137">An XQuery expression that describes the path.</span></span>  
  
3.  <span data-ttu-id="d00ef-138">Hint di ottimizzazione facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-138">Optional optimization hints.</span></span>  
  
 <span data-ttu-id="d00ef-139">Per ulteriori informazioni su questi elementi, vedere [Attività correlate](#reltasks).</span><span class="sxs-lookup"><span data-stu-id="d00ef-139">For more information about these elements, see [Related Tasks](#reltasks).</span></span>  
  

  
## <a name="supported-features-prerequisites-and-limitations"></a><span data-ttu-id="d00ef-140">Funzionalità supportate, prerequisiti e limitazioni</span><span class="sxs-lookup"><span data-stu-id="d00ef-140">Supported Features, Prerequisites, and Limitations</span></span>  
  
###  <a name="supported-xml-features"></a><a name="features"></a> <span data-ttu-id="d00ef-141">Funzionalità XML supportate</span><span class="sxs-lookup"><span data-stu-id="d00ef-141">Supported XML Features</span></span>  
 <span data-ttu-id="d00ef-142">Gli indici XML selettivi supportano l'espressione XQuery, a sua volta supportata da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nei metodi exist(), value() e nodes().</span><span class="sxs-lookup"><span data-stu-id="d00ef-142">Selective XML indexes support the XQuery supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inside the exist(), value() and nodes() methods.</span></span>  
  
-   <span data-ttu-id="d00ef-143">Per i metodi exist(), value() e nodes(), gli indici XML selettivi contengono informazioni sufficienti a trasformare l'intera espressione.</span><span class="sxs-lookup"><span data-stu-id="d00ef-143">For the exist(), value() and nodes() methods, selective XML indexes contain enough information to transform the entire expression.</span></span>  
  
-   <span data-ttu-id="d00ef-144">Per i metodi query() e modify(), gli indici XML selettivi possono essere utilizzati esclusivamente per il filtraggio dei nodi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-144">For the query() and modify() methods, selective XML indexes may be used for node filtering only.</span></span>  
  
-   <span data-ttu-id="d00ef-145">Per il metodo query(), gli indici XML selettivi non vengono utilizzati per recuperare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d00ef-145">For the query() method, selective XML indexes are not used to retrieve results.</span></span>  
  
-   <span data-ttu-id="d00ef-146">Per il metodo modify(), gli indici XML selettivi non vengono utilizzati per aggiornare i documenti XML.</span><span class="sxs-lookup"><span data-stu-id="d00ef-146">For the modify() method, selective XML indexes are not used to update XML documents.</span></span>  
  

  
###  <a name="unsupported-xml-features"></a><a name="unsupported"></a> <span data-ttu-id="d00ef-147">Funzionalità XML non supportate</span><span class="sxs-lookup"><span data-stu-id="d00ef-147">Unsupported XML Features</span></span>  
 <span data-ttu-id="d00ef-148">Gli indici XML selettivi non supportano le seguenti funzionalità supportate nell'implementazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di XML:</span><span class="sxs-lookup"><span data-stu-id="d00ef-148">Selective XML indexes do not support the following features that are supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementation of XML:</span></span>  
  
-   <span data-ttu-id="d00ef-149">Indicizzazione dei nodi con tipi XS complessi: tipi unione, tipi sequenza e tipi elenco.</span><span class="sxs-lookup"><span data-stu-id="d00ef-149">Indexing of nodes with complex XS types: union types, sequence types, and list types.</span></span>  
  
-   <span data-ttu-id="d00ef-150">Indicizzazione di nodi con tipi XS binari: ad esempio, base64Binary e hexBinary.</span><span class="sxs-lookup"><span data-stu-id="d00ef-150">Indexing of nodes with binary XS types: for example, base64Binary and hexBinary.</span></span>  
  
-   <span data-ttu-id="d00ef-151">Specifica dei nodi da indicizzare con espressioni XPath contenenti il carattere jolly `*` come elemento finale: ad esempio,  `/a/b/c/*`, `/a//b/*`o `/a/b/*:c`.</span><span class="sxs-lookup"><span data-stu-id="d00ef-151">Specifying the nodes to index with XPath expressions that contain the wildcard character `*` at the end: For example,  `/a/b/c/*`, `/a//b/*`, or `/a/b/*:c`.</span></span>  
  
-   <span data-ttu-id="d00ef-152">Indicizzazione di un asse diverso da figlio, attributo o discendente.</span><span class="sxs-lookup"><span data-stu-id="d00ef-152">Indexing any axis other than child, attribute, or descendant.</span></span> <span data-ttu-id="d00ef-153">Il case `//<step>` è consentito come case speciale.</span><span class="sxs-lookup"><span data-stu-id="d00ef-153">The `//<step>` case is allowed as a special case.</span></span>  
  
-   <span data-ttu-id="d00ef-154">Indicizzazione di istruzioni di elaborazione XML e commenti.</span><span class="sxs-lookup"><span data-stu-id="d00ef-154">Indexing of XML processing instructions and comments.</span></span>  
  
-   <span data-ttu-id="d00ef-155">Specifica e recupero dell'identificatore di un nodo mediante la funzione id().</span><span class="sxs-lookup"><span data-stu-id="d00ef-155">Specifying and retrieving the identifier for a node by using the id() function.</span></span>  
  

  
###  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="d00ef-156">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d00ef-156">Prerequisites</span></span>  
 <span data-ttu-id="d00ef-157">Sono necessari i prerequisiti indicati di seguito per poter creare un indice XML selettivo per una colonna XML in una tabella utente:</span><span class="sxs-lookup"><span data-stu-id="d00ef-157">The following prerequisites must exist before you can create a selective XML index over an XML column in a user table:</span></span>  
  
-   <span data-ttu-id="d00ef-158">È necessario che esista un indice cluster sulla chiave primaria della tabella utente.</span><span class="sxs-lookup"><span data-stu-id="d00ef-158">A clustered index must exist on the primary key of the user table.</span></span>  
  
-   <span data-ttu-id="d00ef-159">La chiave primaria della tabella utente è limitata a una dimensione di 128 byte quando viene utilizzata con gli indici XML selettivi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-159">The primary key of the user table is limited to a size of 128 bytes when used with selective XML indexes.</span></span>  
  
-   <span data-ttu-id="d00ef-160">La chiave di clustering della tabella utente è limitata a 15 colonne quando viene utilizzata con gli indici XML selettivi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-160">The clustering key of the user table is limited to 15 columns when used with selective XML indexes.</span></span>  
  

  
###  <a name="limitations"></a><a name="limits"></a> <span data-ttu-id="d00ef-161">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="d00ef-161">Limitations</span></span>  
 <span data-ttu-id="d00ef-162">**Requisiti e limitazioni generali**</span><span class="sxs-lookup"><span data-stu-id="d00ef-162">**General requirements and limitations**</span></span>  
  
-   <span data-ttu-id="d00ef-163">Ogni indice XML selettivo deve necessariamente essere creato su una singola colonna XML.</span><span class="sxs-lookup"><span data-stu-id="d00ef-163">Each selective XML index can only be created on a single XML column.</span></span>  
  
-   <span data-ttu-id="d00ef-164">Non è possibile creare un indice XML selettivo su una colonna non di tipo XML.</span><span class="sxs-lookup"><span data-stu-id="d00ef-164">You cannot create a selective XML index on a non-XML column.</span></span>  
  
-   <span data-ttu-id="d00ef-165">Ogni colonna XML in una tabella può includere solo un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-165">Each XML column in a table can have only one selective XML index.</span></span>  
  
-   <span data-ttu-id="d00ef-166">Per ogni tabella è possibile creare al massimo 249 indici XML selettivi.</span><span class="sxs-lookup"><span data-stu-id="d00ef-166">Each table can have up to 249 selective XML indexes.</span></span>  
  
 <span data-ttu-id="d00ef-167">**Limitazioni relative a oggetti supportati**</span><span class="sxs-lookup"><span data-stu-id="d00ef-167">**Limitations on supported objects**</span></span>  
  
 <span data-ttu-id="d00ef-168">Non è possibile creare indici XML selettivi per gli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d00ef-168">You cannot create selective XML indexes on the following objects:</span></span>  
  
1.  <span data-ttu-id="d00ef-169">Colonne XML in una vista.</span><span class="sxs-lookup"><span data-stu-id="d00ef-169">XML columns in a view.</span></span>  
  
2.  <span data-ttu-id="d00ef-170">Variabile con valori di tabella con colonne XML.</span><span class="sxs-lookup"><span data-stu-id="d00ef-170">Table-valued variable with XML columns.</span></span>  
  
3.  <span data-ttu-id="d00ef-171">Variabili di tipo XML.</span><span class="sxs-lookup"><span data-stu-id="d00ef-171">XML type variables.</span></span>  
  
4.  <span data-ttu-id="d00ef-172">Colonne XML calcolate.</span><span class="sxs-lookup"><span data-stu-id="d00ef-172">Computed XML columns.</span></span>  
  
5.  <span data-ttu-id="d00ef-173">Colonne XML con una profondità superiore a 128 nodi nidificati.</span><span class="sxs-lookup"><span data-stu-id="d00ef-173">XML columns with a depth of more than 128 nested nodes.</span></span>  
  
 <span data-ttu-id="d00ef-174">**Limitazioni relative all'archiviazione**</span><span class="sxs-lookup"><span data-stu-id="d00ef-174">**Limitations related to storage**</span></span>  
  
 <span data-ttu-id="d00ef-175">Esiste un limite finito al numero di nodi di un documento XML che è possibile aggiungere all'indice.</span><span class="sxs-lookup"><span data-stu-id="d00ef-175">There is a finite limit on the number of nodes from the XML document that can be added to the index.</span></span> <span data-ttu-id="d00ef-176">Un indice XML selettivo esegue il mapping di documenti XML a una singola tabella relazionale.</span><span class="sxs-lookup"><span data-stu-id="d00ef-176">A selective XML index maps XML documents to a single relational table.</span></span> <span data-ttu-id="d00ef-177">Pertanto non possono essere presenti più di 1.024 colonne non Null in una determinata riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="d00ef-177">Therefore it cannot have more than 1024 non-null columns in any given row of the table.</span></span> <span data-ttu-id="d00ef-178">Inoltre, gran parte delle limitazioni delle colonne di tipo sparse vengono applicate anche agli indici XML selettivi, poiché negli indici vengono utilizzate colonne di tipo sparse per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d00ef-178">Furthermore, many of the limitations of sparse columns also apply to selective XML indexes, because the indexes use sparse columns for storage.</span></span>  
  
 <span data-ttu-id="d00ef-179">Il numero massimo di colonne non Null supportate in qualsiasi riga specificata dipende dalle dimensioni dei dati nelle colonne:</span><span class="sxs-lookup"><span data-stu-id="d00ef-179">The maximum number of non-null columns supported in any given row depends on the size of the data in the columns:</span></span>  
  
-   <span data-ttu-id="d00ef-180">Nel migliore dei casi sono supportate 1024 colonne non Null se tutte le colonne sono di tipo **bit**.</span><span class="sxs-lookup"><span data-stu-id="d00ef-180">In the best case, 1024 non-null columns are supported when all columns are of type **bit**.</span></span>  
  
-   <span data-ttu-id="d00ef-181">Nel peggiore dei casi sono supportate solo 236 colonne non Null se tutte le colonne sono oggetti di grandi dimensioni di tipo **varchar**.</span><span class="sxs-lookup"><span data-stu-id="d00ef-181">In the worst case, only 236 non-null columns are supported when all columns are large objects of type **varchar**.</span></span>  
  
 <span data-ttu-id="d00ef-182">Negli indici XML selettivi vengono utilizzate da una a quattro colonne a livello interno per ogni percorso del nodo indicizzato.</span><span class="sxs-lookup"><span data-stu-id="d00ef-182">Selective XML indexes use from one to four columns internally for every node path that is indexed.</span></span> <span data-ttu-id="d00ef-183">Il numero totale di nodi che è possibile indicizzare varia da 60 a diverse centinaia, a seconda della dimensione effettiva dei dati nei percorsi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="d00ef-183">The total number of nodes that can be indexed ranges from 60 to several hundred nodes, depending on the actual size of the data in the indexed paths.</span></span>  
  
-   <span data-ttu-id="d00ef-184">Nel peggiore dei casi, se qualcuno o tutti i nodi vengono mappati mediante `//` nella definizione del percorso del nodo, il numero massimo di nodi indicizzati è 60.</span><span class="sxs-lookup"><span data-stu-id="d00ef-184">In the worst case, when some or all nodes are mapped using `//` in the node path definition, the maximum number of indexed nodes is 60.</span></span>  
  
-   <span data-ttu-id="d00ef-185">Nel migliore dei casi, se i nodi vengono mappati senza utilizzare `//` nella definizione del percorso del nodo, il numero massimo di nodi indicizzati è 200.</span><span class="sxs-lookup"><span data-stu-id="d00ef-185">In the best case, when nodes are mapped without using `//` in the node path definition, the maximum number of indexed nodes is 200.</span></span>  
  
 <span data-ttu-id="d00ef-186">**Gli indici XML selettivi vengono ricompilati se si esegue un'istruzione CREATE o ALTER per l'indice.**</span><span class="sxs-lookup"><span data-stu-id="d00ef-186">**Selective XML indexes are rebuilt when you CREATE or ALTER the index.**</span></span>  
  
 <span data-ttu-id="d00ef-187">Quando si esegue un'istruzione CREATE o ALTER per un indice XML selettivo, quest'ultimo viene ricompilato in modalità offline a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-187">When you CREATE or ALTER a selective XML index, it is rebuilt in a single-threaded, offline mode.</span></span> <span data-ttu-id="d00ef-188">Le istruzioni ALTER hanno in genere un impatto negativo sulle prestazioni delle query sui documenti XML indicizzati.</span><span class="sxs-lookup"><span data-stu-id="d00ef-188">Frequently ALTER statements negatively affect the performance of queries over the indexed XML documents.</span></span>  
  
 <span data-ttu-id="d00ef-189">**Altre limitazioni**</span><span class="sxs-lookup"><span data-stu-id="d00ef-189">**Other limitations**</span></span>  
  
-   <span data-ttu-id="d00ef-190">Gli indici XML selettivi non sono supportati negli hint per la query.</span><span class="sxs-lookup"><span data-stu-id="d00ef-190">Selective XML indexes are not supported in query hints.</span></span>  
  
-   <span data-ttu-id="d00ef-191">Gli indici XML selettivi e gli indici XML selettivi secondari non sono supportati nell'ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="d00ef-191">Selective XML indexes and secondary selective XML indexes are not supported in Database Tuning Advisor.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="d00ef-192">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="d00ef-192">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d00ef-193">**Attività**</span><span class="sxs-lookup"><span data-stu-id="d00ef-193">**Task**</span></span>|<span data-ttu-id="d00ef-194">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="d00ef-194">**Topic**</span></span>|  
|<span data-ttu-id="d00ef-195">Specificare i percorsi del nodo che si desidera indicizzare e gli hint di ottimizzazione facoltativi quando si crea o si modifica un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-195">Specify the node paths that you want to index and optional optimization hints when you create or alter a selective XML index.</span></span>|[<span data-ttu-id="d00ef-196">Specificare percorsi e hint di ottimizzazione per indici XML selettivi</span><span class="sxs-lookup"><span data-stu-id="d00ef-196">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>](specify-paths-and-optimization-hints-for-selective-xml-indexes.md)|  
|<span data-ttu-id="d00ef-197">Creare, modificare o eliminare un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="d00ef-197">Create, alter, or drop a selective XML index.</span></span>|[<span data-ttu-id="d00ef-198">Creare, modificare o eliminare indici XML selettivi</span><span class="sxs-lookup"><span data-stu-id="d00ef-198">Create, Alter, and Drop Selective XML Indexes</span></span>](create-alter-and-drop-selective-xml-indexes.md)|  
|<span data-ttu-id="d00ef-199">Creare, modificare o eliminare un indice XML selettivo secondario.</span><span class="sxs-lookup"><span data-stu-id="d00ef-199">Create, alter, or drop a secondary selective XML index.</span></span>|[<span data-ttu-id="d00ef-200">Creare, modificare o eliminare indici XML selettivi secondari</span><span class="sxs-lookup"><span data-stu-id="d00ef-200">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>](create-alter-and-drop-secondary-selective-xml-indexes.md)|  
  

  
  
