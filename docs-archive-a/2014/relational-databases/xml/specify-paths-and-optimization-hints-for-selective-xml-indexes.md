---
title: Specificare percorsi e hint di ottimizzazione per indici XML selettivi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 486ee339-165b-4aeb-b760-d2ba023d7d0a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a9d683fe57d489fdb9922b53d2c5c6825835216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719739"
---
# <a name="specify-paths-and-optimization-hints-for-selective-xml-indexes"></a><span data-ttu-id="0db8f-102">Specificare percorsi e hint di ottimizzazione per indici XML selettivi</span><span class="sxs-lookup"><span data-stu-id="0db8f-102">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>
  <span data-ttu-id="0db8f-103">In questo argomento viene descritto come specificare i percorsi del nodo da indicizzare e gli hint di ottimizzazione per l'indicizzazione in fase di creazione o modifica di indici XML selettivi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-103">This topic describes how to specify node paths to index and optimization hints for indexing when you create or alter selective XML indexes.</span></span>  
  
 <span data-ttu-id="0db8f-104">Specificare contemporaneamente i percorsi del nodo e gli hint di ottimizzazione in una delle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0db8f-104">You specify node paths and optimization hints at the same time in one of the following statements:</span></span>  
  
-   <span data-ttu-id="0db8f-105">Nella clausola **FOR** di un'istruzione **CREATE** .</span><span class="sxs-lookup"><span data-stu-id="0db8f-105">In the **FOR** clause of a **CREATE** statement.</span></span> <span data-ttu-id="0db8f-106">Per altre informazioni, vedere [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0db8f-106">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="0db8f-107">Nella clausola **ADD** di un'istruzione **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="0db8f-107">In the **ADD** clause of an **ALTER** statement.</span></span> <span data-ttu-id="0db8f-108">Per altre informazioni, vedere [ALTER INDEX &#40;indici XML selettivi&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="0db8f-108">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="0db8f-109">Per altre informazioni sugli indici XML selettivi, vedere [Indici XML selettivi &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="0db8f-109">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="understanding-xquery-and-sql-server-types-in-untyped-xml"></a><a name="untyped"></a> <span data-ttu-id="0db8f-110">Informazioni sui tipi XQuery e SQL Server in dati XML non tipizzati</span><span class="sxs-lookup"><span data-stu-id="0db8f-110">Understanding XQuery and SQL Server Types in Untyped XML</span></span>  
 <span data-ttu-id="0db8f-111">Negli indici XML selettivi sono supportati due sistemi di tipi: tipi XQuery e tipi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0db8f-111">Selective XML indexes support two type systems: XQuery types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="0db8f-112">Il percorso indicizzato può essere utilizzato per la corrispondenza di un'espressione XQuery o del tipo restituito del metodo value() del tipo di dati XML.</span><span class="sxs-lookup"><span data-stu-id="0db8f-112">The indexed path can be used either to match an XQuery expression, or to match the return type of the value() method of the XML data type.</span></span>  
  
-   <span data-ttu-id="0db8f-113">Se un percorso da indicizzare non viene annotato oppure viene annotato con la parola chiave XQUERY, il percorso corrisponde a un'espressione XQuery.</span><span class="sxs-lookup"><span data-stu-id="0db8f-113">When a path to index is not annotated, or is annotated with the XQUERY keyword, the path matches an XQuery expression.</span></span> <span data-ttu-id="0db8f-114">Esistono due varianti per i percorsi dei nodi con annotazioni XQuery:</span><span class="sxs-lookup"><span data-stu-id="0db8f-114">There are two variations for XQUERY-annotated node paths:</span></span>  
  
    -   <span data-ttu-id="0db8f-115">Se non si specificano la parola chiave XQUERY e il tipo di dati XQuery, vengono utilizzati i mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0db8f-115">If you do not specify the XQUERY keyword and the XQuery data type, then default mappings are used.</span></span> <span data-ttu-id="0db8f-116">In genere le prestazioni e l'archiviazione non raggiungono livelli ottimali.</span><span class="sxs-lookup"><span data-stu-id="0db8f-116">Typically performance and storage are not optimal.</span></span>  
  
    -   <span data-ttu-id="0db8f-117">Se si specificano la parola chiave XQUERY e il tipo di dati XQuery (e facoltativamente altri hint di ottimizzazione), è possibile ottenere prestazioni ottimali e un livello estremamente efficiente di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0db8f-117">If you specify the XQUERY keyword and the XQuery data type, and optionally other optimization hints, then you can achieve the best possible performance and the most efficient possible storage.</span></span> <span data-ttu-id="0db8f-118">Un cast potrebbe tuttavia avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-118">However, a cast can fail.</span></span>  
  
-   <span data-ttu-id="0db8f-119">Se un percorso da indicizzare viene annotato con la parola chiave SQL, il percorso corrisponde al tipo restituito del metodo value() del tipo di dati XML.</span><span class="sxs-lookup"><span data-stu-id="0db8f-119">When a path to index is annotated with the SQL keyword, the path matches the return type of the value() method of the XML data type.</span></span> <span data-ttu-id="0db8f-120">Specificare il tipo di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriato, ovvero il tipo restituito previsto dal metodo value().</span><span class="sxs-lookup"><span data-stu-id="0db8f-120">Specify the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, which is the return type that you expect from the value() method.</span></span>  
  
 <span data-ttu-id="0db8f-121">Esistono differenze minime tra il sistema di tipi XML di espressioni XQuery e il sistema di tipi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validi per il metodo value() del tipo di dati XML.</span><span class="sxs-lookup"><span data-stu-id="0db8f-121">There are subtle differences between the XQuery expressions XML type system and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type system applied to the value() method of the XML data type.</span></span> <span data-ttu-id="0db8f-122">Di seguito sono riportate queste differenze:</span><span class="sxs-lookup"><span data-stu-id="0db8f-122">These differences include the following:</span></span>  
  
-   <span data-ttu-id="0db8f-123">Il sistema di tipi XQuery riconosce gli spazi finali.</span><span class="sxs-lookup"><span data-stu-id="0db8f-123">The XQuery type system is aware of trailing spaces.</span></span> <span data-ttu-id="0db8f-124">Ad esempio, in base alla semantica del tipo XQuery, le stringhe "abc" e "abc " non sono uguali, a differenza di quanto accade in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0db8f-124">For example, according to XQuery type semantics, the strings "abc" and "abc " are not equal, while in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] these strings are equal.</span></span>  
  
-   <span data-ttu-id="0db8f-125">I tipi di dati a virgola mobile XQuery supportano valori speciali di +/- zero e +/- infinito.</span><span class="sxs-lookup"><span data-stu-id="0db8f-125">XQuery floating point data types support special values of +/- zero and +/- infinity.</span></span> <span data-ttu-id="0db8f-126">Questi valori speciali non sono supportati nei tipi di dati a virgola mobile [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0db8f-126">These special values are not supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] floating point data types.</span></span>  
  
### <a name="xquery-types-in-untyped-xml"></a><span data-ttu-id="0db8f-127">Tipi XQuery in dati XML non tipizzati</span><span class="sxs-lookup"><span data-stu-id="0db8f-127">XQuery Types in Untyped XML</span></span>  
  
-   <span data-ttu-id="0db8f-128">I tipi XQuery corrispondono alle espressioni XQuery in tutti i metodi del tipo di dati XML, incluso il metodo value().</span><span class="sxs-lookup"><span data-stu-id="0db8f-128">XQuery types match XQuery expressions in all methods of the XML data type including the value() method.</span></span>  
  
-   <span data-ttu-id="0db8f-129">I tipi XQuery supportano questi hint di ottimizzazione: node(), SINGLETON, DATA TYPE e MAXLENGTH.</span><span class="sxs-lookup"><span data-stu-id="0db8f-129">XQuery types support these optimization hints: node(), SINGLETON, DATA TYPE, and MAXLENGTH.</span></span>  
  
 <span data-ttu-id="0db8f-130">Per le espressioni XQuery in dati XML non tipizzati, è possibile scegliere tra due modalità di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="0db8f-130">For XQuery expressions over untyped XML, you can choose between two modes of operation:</span></span>  
  
-   <span data-ttu-id="0db8f-131">**Modalità di mapping predefinito**.</span><span class="sxs-lookup"><span data-stu-id="0db8f-131">**Default mapping mode**.</span></span> <span data-ttu-id="0db8f-132">In questa modalità è necessario specificare solo il percorso in fase di creazione di un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-132">In this mode, you specify only the path when creating a selective XML index.</span></span>  
  
-   <span data-ttu-id="0db8f-133">**Modalità di mapping definito dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="0db8f-133">**User-specified mapping mode**.</span></span> <span data-ttu-id="0db8f-134">In questa modalità è necessario specificare il percorso e hint di ottimizzazione facoltativi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-134">In this mode, you specify both the path and optional optimization hints.</span></span>  
  
 <span data-ttu-id="0db8f-135">Nella modalità di mapping predefinito viene utilizzata un'opzione di archiviazione conservativa, generica e sempre sicura.</span><span class="sxs-lookup"><span data-stu-id="0db8f-135">The default mapping mode uses a conservative storage option which is always safe and general.</span></span> <span data-ttu-id="0db8f-136">Può corrispondere a qualsiasi tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="0db8f-136">It can match any expression type.</span></span> <span data-ttu-id="0db8f-137">Alcune limitazioni della modalità di mapping predefinito sono rappresentate da prestazioni non ottimali, dovute alla necessità di eseguire un numero maggiore di cast di runtime, e dalla mancanza di indici secondari.</span><span class="sxs-lookup"><span data-stu-id="0db8f-137">A limitation of the default mapping mode is less than optimal performance, because an increased number of runtime casts are required, and secondary indexes are not available.</span></span>  
  
 <span data-ttu-id="0db8f-138">Di seguito è riportato un esempio di un indice XML selettivo creato con mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0db8f-138">Here is an example of a selective XML index created with default mappings.</span></span> <span data-ttu-id="0db8f-139">Per tutti e tre i percorsi vengono usati il tipo di nodo predefinito (**xs:untypedAtomic**) e la cardinalità.</span><span class="sxs-lookup"><span data-stu-id="0db8f-139">For all three paths, the default node type (**xs:untypedAtomic**) and cardinality are used.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_default  
ON Tbl(xmlcol)  
FOR  
(  
mypath01 =  '/a/b',  
mypath02 = '/a/b/c',  
mypath03 = '/a/b/d'  
)  
```  
  
 <span data-ttu-id="0db8f-140">La modalità di mapping definito dall'utente consente di specificare un tipo e la cardinalità del nodo per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="0db8f-140">The user-specified mapping mode lets you specify a type and cardinality for the node to obtain better performance.</span></span> <span data-ttu-id="0db8f-141">Questo miglioramento delle prestazioni viene tuttavia conseguito a discapito della sicurezza, perché un cast potrebbe avere esito negativo, e della generalità, perché la corrispondenza con l'indice XML selettivo viene rilevata solo per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="0db8f-141">However, this improved performance is achieved by giving up safety - because a cast can fail - and generality - because only the specified type is matched with the selective XML index.</span></span>  
  
 <span data-ttu-id="0db8f-142">Di seguito sono indicati i tipi XQuery supportati per i dati XML non tipizzati:</span><span class="sxs-lookup"><span data-stu-id="0db8f-142">The XQuery types supported for untyped XML case are:</span></span>  
  
-   <span data-ttu-id="0db8f-143">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="0db8f-143">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="0db8f-144">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="0db8f-144">**xs:double**</span></span>  
  
-   <span data-ttu-id="0db8f-145">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="0db8f-145">**xs:string**</span></span>  
  
-   <span data-ttu-id="0db8f-146">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="0db8f-146">**xs:date**</span></span>  
  
-   <span data-ttu-id="0db8f-147">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="0db8f-147">**xs:time**</span></span>  
  
-   <span data-ttu-id="0db8f-148">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="0db8f-148">**xs:dateTime**</span></span>  
  
 <span data-ttu-id="0db8f-149">Se il tipo viene omesso, il nodo verrà considerato del tipo di dati **xs:untypedAtomic** .</span><span class="sxs-lookup"><span data-stu-id="0db8f-149">If the type is not specified, the node is assumed to be of the **xs:untypedAtomic** data type.</span></span>  
  
 <span data-ttu-id="0db8f-150">È possibile ottimizzare l'indice XML selettivo visualizzato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0db8f-150">You can optimize the selective XML index shown in the following manner:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_optimized  
ON Tbl(xmlcol)  
FOR  
(  
mypath= '/a/b' as XQUERY 'node()',  
pathX = '/a/b/c' as XQUERY 'xs:double' SINGLETON,  
pathY = '/a/b/d' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
)  
-- mypath - Only the node value is needed; storage is saved.  
-- pathX - Performance is improved; secondary indexes are possible.  
-- pathY - Performance is improved; secondary indexes are possible; storage is saved.  
```  
  
### <a name="sql-server-types-in-untyped-xml"></a><span data-ttu-id="0db8f-151">Tipi SQL Server in dati XML non tipizzati</span><span class="sxs-lookup"><span data-stu-id="0db8f-151">SQL Server Types in Untyped XML</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0db8f-152">i tipi corrispondono al valore restituito del metodo value().</span><span class="sxs-lookup"><span data-stu-id="0db8f-152">types match the return value of the value() method.</span></span>  
  
-   <span data-ttu-id="0db8f-153">I tipi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supportano l'hint di ottimizzazione SINGLETON.</span><span class="sxs-lookup"><span data-stu-id="0db8f-153">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types support this optimization hint: SINGLETON.</span></span>  
  
 <span data-ttu-id="0db8f-154">È obbligatori specificare un tipo per i percorsi che restituiscono i tipi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0db8f-154">Specifying a type is mandatory for paths that return [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="0db8f-155">Utilizzare lo stesso tipo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che verrebbe utilizzato nel metodo value().</span><span class="sxs-lookup"><span data-stu-id="0db8f-155">Use the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type that you would use in the value() method.</span></span>  
  
 <span data-ttu-id="0db8f-156">Si consideri la query seguente:</span><span class="sxs-lookup"><span data-stu-id="0db8f-156">Consider the following query:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/d)[1]', 'NVARCHAR(200)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="0db8f-157">La query specificata restituisce un valore dal percorso `/a/b/d` all'interno di un tipo di dati NVARCHAR(200), in modo che il tipo di dati da specificare per il nodo sia facilmente intuibile.</span><span class="sxs-lookup"><span data-stu-id="0db8f-157">The specified query returns a value from the path `/a/b/d` packed into an NVARCHAR(200) data type, so the data type to specify for the node is obvious.</span></span> <span data-ttu-id="0db8f-158">Non esiste tuttavia uno schema per specificare la cardinalità del nodo in dati XML non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="0db8f-158">However there is no schema to specify the cardinality of the node in untyped XML.</span></span> <span data-ttu-id="0db8f-159">Per specificare che il nodo `d` venga visualizzato al massimo una volta nel nodo padre `b`, creare un indice XML selettivo in cui venga utilizzato l'hint di ottimizzazione SINGLETON nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0db8f-159">To specify that node `d` appears at most once under its parent node `b`, create a selective XML index that uses the SINGLETON optimization hint as follows:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_US  
ON Tbl(xmlcol)  
FOR  
(  
node1223 = '/a/b/d' as SQL NVARCHAR(200) SINGLETON  
)  
```  
  

  
##  <a name="understanding-selective-xml-index-support-for-typed-xml"></a><a name="typed"></a> <span data-ttu-id="0db8f-160">Informazioni sul supporto degli indici XML selettivi per dati XML tipizzati</span><span class="sxs-lookup"><span data-stu-id="0db8f-160">Understanding Selective XML Index support for typed XML</span></span>  
 <span data-ttu-id="0db8f-161">I dati XML tipizzati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rappresentano uno schema associato a uno specifico documento XML.</span><span class="sxs-lookup"><span data-stu-id="0db8f-161">Typed XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is a schema associated with a given XML document.</span></span> <span data-ttu-id="0db8f-162">Lo schema definisce la struttura generica del documento e i tipi di nodi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-162">The schema defines overall document structure and types of nodes.</span></span> <span data-ttu-id="0db8f-163">Se esiste uno schema, l'indice XML selettivo applica la sua struttura quando l'utente promuove i percorsi, pertanto non è necessario specificare i tipi XQUERY per i percorsi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-163">If a schema exists, Selective XML Index applies the schema structure when the user promotes paths, so there is no need to specify the XQUERY types for paths.</span></span>  
  
 <span data-ttu-id="0db8f-164">Nell'indice XML selettivo vengono supportati i tipi XSD seguenti:</span><span class="sxs-lookup"><span data-stu-id="0db8f-164">Selective XML Index supports following XSD types:</span></span>  
  
-   <span data-ttu-id="0db8f-165">**xs:anyUri**</span><span class="sxs-lookup"><span data-stu-id="0db8f-165">**xs:anyUri**</span></span>  
  
-   <span data-ttu-id="0db8f-166">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="0db8f-166">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="0db8f-167">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="0db8f-167">**xs:date**</span></span>  
  
-   <span data-ttu-id="0db8f-168">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="0db8f-168">**xs:dateTime**</span></span>  
  
-   <span data-ttu-id="0db8f-169">**xs:day**</span><span class="sxs-lookup"><span data-stu-id="0db8f-169">**xs:day**</span></span>  
  
-   <span data-ttu-id="0db8f-170">**xs: decimal**</span><span class="sxs-lookup"><span data-stu-id="0db8f-170">**xs:decimal**</span></span>  
  
-   <span data-ttu-id="0db8f-171">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="0db8f-171">**xs:double**</span></span>  
  
-   <span data-ttu-id="0db8f-172">**xs:float**</span><span class="sxs-lookup"><span data-stu-id="0db8f-172">**xs:float**</span></span>  
  
-   <span data-ttu-id="0db8f-173">**xs:int**</span><span class="sxs-lookup"><span data-stu-id="0db8f-173">**xs:int**</span></span>  
  
-   <span data-ttu-id="0db8f-174">**xs:integer**</span><span class="sxs-lookup"><span data-stu-id="0db8f-174">**xs:integer**</span></span>  
  
-   <span data-ttu-id="0db8f-175">**xs:language**</span><span class="sxs-lookup"><span data-stu-id="0db8f-175">**xs:language**</span></span>  
  
-   <span data-ttu-id="0db8f-176">**xs:long**</span><span class="sxs-lookup"><span data-stu-id="0db8f-176">**xs:long**</span></span>  
  
-   <span data-ttu-id="0db8f-177">**xs:name**</span><span class="sxs-lookup"><span data-stu-id="0db8f-177">**xs:name**</span></span>  
  
-   <span data-ttu-id="0db8f-178">**xs:NCName**</span><span class="sxs-lookup"><span data-stu-id="0db8f-178">**xs:NCName**</span></span>  
  
-   <span data-ttu-id="0db8f-179">**xs:negativeInteger**</span><span class="sxs-lookup"><span data-stu-id="0db8f-179">**xs:negativeInteger**</span></span>  
  
-   <span data-ttu-id="0db8f-180">**xs:nmtoken**</span><span class="sxs-lookup"><span data-stu-id="0db8f-180">**xs:nmtoken**</span></span>  
  
-   <span data-ttu-id="0db8f-181">**xs:nonNegativeInteger**</span><span class="sxs-lookup"><span data-stu-id="0db8f-181">**xs:nonNegativeInteger**</span></span>  
  
-   <span data-ttu-id="0db8f-182">**xs:nonPositiveInteger**</span><span class="sxs-lookup"><span data-stu-id="0db8f-182">**xs:nonPositiveInteger**</span></span>  
  
-   <span data-ttu-id="0db8f-183">**xs:positiveInteger**</span><span class="sxs-lookup"><span data-stu-id="0db8f-183">**xs:positiveInteger**</span></span>  
  
-   <span data-ttu-id="0db8f-184">**xs:qname**</span><span class="sxs-lookup"><span data-stu-id="0db8f-184">**xs:qname**</span></span>  
  
-   <span data-ttu-id="0db8f-185">**xs:short**</span><span class="sxs-lookup"><span data-stu-id="0db8f-185">**xs:short**</span></span>  
  
-   <span data-ttu-id="0db8f-186">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="0db8f-186">**xs:string**</span></span>  
  
-   <span data-ttu-id="0db8f-187">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="0db8f-187">**xs:time**</span></span>  
  
-   <span data-ttu-id="0db8f-188">**xs:token**</span><span class="sxs-lookup"><span data-stu-id="0db8f-188">**xs:token**</span></span>  
  
-   <span data-ttu-id="0db8f-189">**xs:unsignedByte**</span><span class="sxs-lookup"><span data-stu-id="0db8f-189">**xs:unsignedByte**</span></span>  
  
-   <span data-ttu-id="0db8f-190">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="0db8f-190">**xs:unsignedInt**</span></span>  
  
-   <span data-ttu-id="0db8f-191">**xs:unsignedLong**</span><span class="sxs-lookup"><span data-stu-id="0db8f-191">**xs:unsignedLong**</span></span>  
  
-   <span data-ttu-id="0db8f-192">**xs:unsignedShort**</span><span class="sxs-lookup"><span data-stu-id="0db8f-192">**xs:unsignedShort**</span></span>  
  
 <span data-ttu-id="0db8f-193">Quando viene creato un indice XML selettivo in un documento con uno schema associato, se si specifica un tipo XQUERY in fase di creazione o modifica dell'indice, verrà restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="0db8f-193">When Selective XML Index is created over a document that has schema associated with it, specifying a XQUERY type at index creation or altering returns an error.</span></span> <span data-ttu-id="0db8f-194">L'utente può utilizzare annotazioni di tipo SQL nell'ambito della promozione del percorso.</span><span class="sxs-lookup"><span data-stu-id="0db8f-194">The user can use SQL type annotations in the path promotion part.</span></span> <span data-ttu-id="0db8f-195">Il tipo SQL deve essere una conversione valida del tipo CLR definito nello schema. In caso contrario, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="0db8f-195">The SQL type must be a valid conversion from the XSD type defined in the schema, or an error is thrown.</span></span> <span data-ttu-id="0db8f-196">Sono supportati tutti i tipi SQL con una rappresentazione appropriata in XSD, ad eccezione dei tipi date/time.</span><span class="sxs-lookup"><span data-stu-id="0db8f-196">All SQL types that have adequate representation in XSD are supported, with an exception of date/time types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0db8f-197">L'indice selettivo viene utilizzato se il tipo specificato nella promozione del percorso dell'indice XML selettivo corrisponde al valore restituito del metodo value().</span><span class="sxs-lookup"><span data-stu-id="0db8f-197">The selective index is used if the type specified in the Selective XML Index path promotion is the same as the value() method return value.</span></span>  
  
 <span data-ttu-id="0db8f-198">Con i documenti XML tipizzati è possibile utilizzare gli hint di ottimizzazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0db8f-198">The following optimization hints can be used with typed XML documents:</span></span>  
  
-   <span data-ttu-id="0db8f-199">hint di ottimizzazione node().</span><span class="sxs-lookup"><span data-stu-id="0db8f-199">node() optimization hint.</span></span>  
  
-   <span data-ttu-id="0db8f-200">L'hint di ottimizzazione MAXLENGTH può essere utilizzato con tipi xs:string per abbreviare il valore indicizzato.</span><span class="sxs-lookup"><span data-stu-id="0db8f-200">MAXLENGTH optimization hint can be used with xs:string types to shorten the indexed value.</span></span>  
  
 <span data-ttu-id="0db8f-201">Per altre informazioni sugli hint di ottimizzazione, vedere [Specifica di hint di ottimizzazione](#hints).</span><span class="sxs-lookup"><span data-stu-id="0db8f-201">For more information about optimization hints, see [Specifying Optimization Hints](#hints).</span></span>  
  
##  <a name="specifying-paths"></a><a name="paths"></a> <span data-ttu-id="0db8f-202">Specifica di percorsi</span><span class="sxs-lookup"><span data-stu-id="0db8f-202">Specifying Paths</span></span>  
 <span data-ttu-id="0db8f-203">Un indice XML selettivo consente di indicizzare solo un subset di nodi dai dati XML archiviati rilevanti per le query che si intende eseguire.</span><span class="sxs-lookup"><span data-stu-id="0db8f-203">A selective XML index lets you index only a subset of nodes from the stored XML data that are relevant for the queries that you expect to run.</span></span> <span data-ttu-id="0db8f-204">Se il subset dei nodi correlati è nettamente inferiore al numero totale di nodi nel documento XML, nell'indice XML selettivo vengono archiviati solo i nodi rilevanti.</span><span class="sxs-lookup"><span data-stu-id="0db8f-204">When the subset of relevant nodes is much smaller than the total number of nodes in the XML document, the selective XML index stores only the relevant nodes.</span></span> <span data-ttu-id="0db8f-205">Per trarre vantaggio da un indice XML selettivo, identificare il corretto subset di nodi da indicizzare.</span><span class="sxs-lookup"><span data-stu-id="0db8f-205">To benefit from a selective XML index, identify the correct subset of nodes to index.</span></span>  
  
### <a name="choosing-the-nodes-to-index"></a><span data-ttu-id="0db8f-206">Scelta dei nodi da indicizzare</span><span class="sxs-lookup"><span data-stu-id="0db8f-206">Choosing the nodes to index</span></span>  
 <span data-ttu-id="0db8f-207">Per identificare il subset corretto di nodi da aggiungere a un indice XML selettivo, è possibile utilizzare i due semplici principi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="0db8f-207">You can use the following two simple principles to identify the correct subset of nodes to add to a selective XML index.</span></span>  
  
1.  <span data-ttu-id="0db8f-208">**Principio 1**: per valutare una specifica espressione XQuery, indicizzare tutti i nodi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="0db8f-208">**Principle 1**: To evaluate a given XQuery expression, index all nodes that you need to examine.</span></span>  
  
    -   <span data-ttu-id="0db8f-209">Indicizzare tutti i nodi la cui esistenza o il cui valore viene utilizzato nell'espressione XQuery.</span><span class="sxs-lookup"><span data-stu-id="0db8f-209">Index all nodes whose existence or value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="0db8f-210">Indicizzare tutti i nodi dell'espressione XQuery in cui vengono applicati predicati XQuery.</span><span class="sxs-lookup"><span data-stu-id="0db8f-210">Index all nodes in the XQuery expression on which XQuery predicates are applied.</span></span>  
  
     <span data-ttu-id="0db8f-211">Si consideri la semplice query sul [documento XML di esempio](#sample) in questo argomento:</span><span class="sxs-lookup"><span data-stu-id="0db8f-211">Consider the following simple query over the [sample XML document](#sample) in this topic:</span></span>  
  
    ```sql  
    SELECT T.record FROM myXMLTable T  
    WHERE T.xmldata.exist('/a/b[./c = "43"]') = 1  
    ```  
  
     <span data-ttu-id="0db8f-212">Per restituire istanze XML che soddisfano la query, un indice XML selettivo deve esaminare due nodi in ogni istanza XML:</span><span class="sxs-lookup"><span data-stu-id="0db8f-212">In order to return the XML instances that satisfy this query, a selective XML index needs to examine two nodes in every XML instance:</span></span>  
  
    -   <span data-ttu-id="0db8f-213">Il nodo `c`, in quanto il rispettivo valore viene utilizzato nell'espressione XQuery.</span><span class="sxs-lookup"><span data-stu-id="0db8f-213">Node `c`, because its value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="0db8f-214">Il nodo `b`, poiché viene applicato un predicato per il nodo`b` nell'espressione XQuery.</span><span class="sxs-lookup"><span data-stu-id="0db8f-214">Node `b`, because a predicate is applied over node`b` in the XQuery expression.</span></span>  
  
2.  <span data-ttu-id="0db8f-215">**Principio 2**: per ottenere prestazioni ottimali, indicizzare tutti i nodi necessari per valutare una specifica espressione XQuery.</span><span class="sxs-lookup"><span data-stu-id="0db8f-215">**Principle 2**: For best performance, index all nodes that are required to evaluate a given XQuery expression.</span></span> <span data-ttu-id="0db8f-216">Se si indicizzano solo alcuni nodi, l'indice XML selettivo migliora la valutazione delle sottoespressioni che includono solo nodi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="0db8f-216">If you index only some of the nodes, then the selective XML index improves the evaluation of sub-expressions that include only indexed nodes.</span></span>  
  
 <span data-ttu-id="0db8f-217">Per migliorare le prestazioni dell'istruzione SELECT precedentemente illustrata, è possibile creare l'indice XML selettivo seguente:</span><span class="sxs-lookup"><span data-stu-id="0db8f-217">To improve the performance of the SELECT statement shown above, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX simple_sxi  
ON Tbl(xmlcol)  
FOR  
(  
    path123 =  '/a/b',  
    path124 =  '/a/b/c'  
)  
```  
  
### <a name="indexing-identical-paths"></a><span data-ttu-id="0db8f-218">Indicizzazione di percorsi identici</span><span class="sxs-lookup"><span data-stu-id="0db8f-218">Indexing identical paths</span></span>  
 <span data-ttu-id="0db8f-219">Non è possibile promuovere percorsi identici come tipo di dati identico in nomi di percorso diversi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-219">You cannot promote identical paths as the same data type under different path names.</span></span> <span data-ttu-id="0db8f-220">Ad esempio, la query seguente genera un errore, in quanto `pathOne` e `pathTwo` sono identici:</span><span class="sxs-lookup"><span data-stu-id="0db8f-220">For example, the following query raises an error, because `pathOne` and `pathTwo` are identical:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:string',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
 <span data-ttu-id="0db8f-221">È tuttavia possibile promuovere percorsi diversi come tipi di dati diversi con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-221">However, you can promote identical paths as different data types with different names.</span></span> <span data-ttu-id="0db8f-222">Ad esempio, la query seguente è accettabile, poiché i tipi di dati sono diversi:</span><span class="sxs-lookup"><span data-stu-id="0db8f-222">For example, the following query is now acceptable, because the data types are different:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:double',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
### <a name="examples"></a><span data-ttu-id="0db8f-223">Esempi</span><span class="sxs-lookup"><span data-stu-id="0db8f-223">Examples</span></span>  
 <span data-ttu-id="0db8f-224">Di seguito sono riportati alcuni esempi aggiuntivi di scelta dei nodi corretti da indicizzare per tipi XQuery diversi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-224">Here are some additional examples of selecting the correct nodes to index for different XQuery types.</span></span>  
  
 <span data-ttu-id="0db8f-225">**Esempio 1**</span><span class="sxs-lookup"><span data-stu-id="0db8f-225">**Example 1**</span></span>  
  
 <span data-ttu-id="0db8f-226">Di seguito è riportata una semplice espressione XQuery in cui viene utilizzato il metodo exist():</span><span class="sxs-lookup"><span data-stu-id="0db8f-226">Here is a simple XQuery that uses the exist() method:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e/h') = 1  
```  
  
 <span data-ttu-id="0db8f-227">Nella tabella seguente vengono indicati i nodi da indicizzare per consentire l'utilizzo dell'indice XML selettivo da parte della query.</span><span class="sxs-lookup"><span data-stu-id="0db8f-227">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="0db8f-228">Nodo da includere nell'indice</span><span class="sxs-lookup"><span data-stu-id="0db8f-228">Node to include in the index</span></span>|<span data-ttu-id="0db8f-229">Motivo alla base dell'indicizzazione del nodo</span><span class="sxs-lookup"><span data-stu-id="0db8f-229">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="0db8f-230">**/a/b/c/d/e/h**</span><span class="sxs-lookup"><span data-stu-id="0db8f-230">**/a/b/c/d/e/h**</span></span>|<span data-ttu-id="0db8f-231">L'esistenza del nodo `h` viene valutata nel metodo exist().</span><span class="sxs-lookup"><span data-stu-id="0db8f-231">The existence of node `h` is evaluated in the exist() method.</span></span>|  
  
 <span data-ttu-id="0db8f-232">**Esempio 2**</span><span class="sxs-lookup"><span data-stu-id="0db8f-232">**Example 2**</span></span>  
  
 <span data-ttu-id="0db8f-233">Di seguito è riportata una variante più complessa dell'espressione XQuery precedente, con un predicato applicato:</span><span class="sxs-lookup"><span data-stu-id="0db8f-233">Here is a more complex variation of the previous XQuery, with a predicate applied:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e[./f = "SQL"]') = 1  
```  
  
 <span data-ttu-id="0db8f-234">Nella tabella seguente vengono indicati i nodi da indicizzare per consentire l'utilizzo dell'indice XML selettivo da parte della query.</span><span class="sxs-lookup"><span data-stu-id="0db8f-234">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="0db8f-235">Nodo da includere nell'indice</span><span class="sxs-lookup"><span data-stu-id="0db8f-235">Node to include in the index</span></span>|<span data-ttu-id="0db8f-236">Motivo alla base dell'indicizzazione del nodo</span><span class="sxs-lookup"><span data-stu-id="0db8f-236">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="0db8f-237">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="0db8f-237">**/a/b/c/d/e**</span></span>|<span data-ttu-id="0db8f-238">Viene applicato un predicato per il nodo `e`.</span><span class="sxs-lookup"><span data-stu-id="0db8f-238">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="0db8f-239">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="0db8f-239">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="0db8f-240">Il valore del nodo `f` viene valutato nel predicato.</span><span class="sxs-lookup"><span data-stu-id="0db8f-240">The value of node `f` is evaluated inside the predicate.</span></span>|  
  
 <span data-ttu-id="0db8f-241">**Esempio 3**</span><span class="sxs-lookup"><span data-stu-id="0db8f-241">**Example 3**</span></span>  
  
 <span data-ttu-id="0db8f-242">Di seguito è riportata una query più complessa con una clausola value():</span><span class="sxs-lookup"><span data-stu-id="0db8f-242">Here is a more complex query with a value() clause:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/c/d/e[./f = "SQL"]/g)[1]', 'nvarchar(100)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="0db8f-243">Nella tabella seguente vengono indicati i nodi da indicizzare per consentire l'utilizzo dell'indice XML selettivo da parte della query.</span><span class="sxs-lookup"><span data-stu-id="0db8f-243">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="0db8f-244">Nodo da includere nell'indice</span><span class="sxs-lookup"><span data-stu-id="0db8f-244">Node to include in the index</span></span>|<span data-ttu-id="0db8f-245">Motivo alla base dell'indicizzazione del nodo</span><span class="sxs-lookup"><span data-stu-id="0db8f-245">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="0db8f-246">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="0db8f-246">**/a/b/c/d/e**</span></span>|<span data-ttu-id="0db8f-247">Viene applicato un predicato per il nodo `e`.</span><span class="sxs-lookup"><span data-stu-id="0db8f-247">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="0db8f-248">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="0db8f-248">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="0db8f-249">Il valore del nodo `f` viene valutato nel predicato.</span><span class="sxs-lookup"><span data-stu-id="0db8f-249">The value of node `f` is evaluated inside the predicate.</span></span>|  
|<span data-ttu-id="0db8f-250">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="0db8f-250">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="0db8f-251">Il valore del nodo `g` viene restituito dal metodo value().</span><span class="sxs-lookup"><span data-stu-id="0db8f-251">The value of node `g` is returned by the value() method.</span></span>|  
  
 <span data-ttu-id="0db8f-252">**Esempio 4**</span><span class="sxs-lookup"><span data-stu-id="0db8f-252">**Example 4**</span></span>  
  
 <span data-ttu-id="0db8f-253">Di seguito è riportata una query in cui viene utilizzata una clausola FLWOR in una clausola exist().</span><span class="sxs-lookup"><span data-stu-id="0db8f-253">Here is a query that uses a FLWOR clause inside an exist() clause.</span></span> <span data-ttu-id="0db8f-254">Il nome FLWOR deriva dalle cinque clausole che possono costituire un'espressione XQuery FLWOR: for, let, where, order by e return.</span><span class="sxs-lookup"><span data-stu-id="0db8f-254">(The name FLWOR comes from the five clauses that can make up an XQuery FLWOR expression: for, let, where, order by, and return.)</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('  
  For $x in /a/b/c/d/e  
  Where $x/f = "SQL"  
  Return $x/g  
') = 1  
```  
  
 <span data-ttu-id="0db8f-255">Nella tabella seguente vengono indicati i nodi da indicizzare per consentire l'utilizzo dell'indice XML selettivo da parte della query.</span><span class="sxs-lookup"><span data-stu-id="0db8f-255">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="0db8f-256">Nodo da includere nell'indice</span><span class="sxs-lookup"><span data-stu-id="0db8f-256">Node to include in the index</span></span>|<span data-ttu-id="0db8f-257">Motivo alla base dell'indicizzazione del nodo</span><span class="sxs-lookup"><span data-stu-id="0db8f-257">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="0db8f-258">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="0db8f-258">**/a/b/c/d/e**</span></span>|<span data-ttu-id="0db8f-259">L'esistenza del nodo `e` viene valutata nella clausola FLWOR.</span><span class="sxs-lookup"><span data-stu-id="0db8f-259">The existence of node `e` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="0db8f-260">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="0db8f-260">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="0db8f-261">Il valore del nodo `f` viene valutato nella clausola FLWOR.</span><span class="sxs-lookup"><span data-stu-id="0db8f-261">The value of node `f` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="0db8f-262">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="0db8f-262">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="0db8f-263">L'esistenza del nodo `g` viene valutata dal metodo exist().</span><span class="sxs-lookup"><span data-stu-id="0db8f-263">The existence of node `g` is evaluated by the exist() method.</span></span>|  
  

  
##  <a name="specifying-optimization-hints"></a><a name="hints"></a> <span data-ttu-id="0db8f-264">Specifica di hint di ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="0db8f-264">Specifying Optimization Hints</span></span>  
 <span data-ttu-id="0db8f-265">È possibile utilizzare hint di ottimizzazione facoltativi per specificare ulteriori dettagli sul mapping per un nodo indicizzato da un indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-265">You can use optional optimization hints to specify additional mapping details for a node indexed by a selective XML index.</span></span> <span data-ttu-id="0db8f-266">È ad esempio possibile specificare il tipo di dati e la cardinalità del nodo, nonché determinate informazioni sulla struttura dei dati.</span><span class="sxs-lookup"><span data-stu-id="0db8f-266">For example, you can specify the data type and cardinality of the node, and certain information about the structure of the data.</span></span> <span data-ttu-id="0db8f-267">Queste informazioni aggiuntive garantiscono un mapping più efficiente,</span><span class="sxs-lookup"><span data-stu-id="0db8f-267">This additional information supports better mapping.</span></span> <span data-ttu-id="0db8f-268">oltre a determinare miglioramenti nelle prestazioni o risparmi in termini di archiviazione, se non entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-268">It also results in improvements in performance or savings in storage, or both.</span></span>  
  
 <span data-ttu-id="0db8f-269">L'utilizzo di hint di ottimizzazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-269">The use of optimization hints is optional.</span></span> <span data-ttu-id="0db8f-270">È sempre possibile accettare i mapping predefiniti, affidabili ma non necessariamente in grado di garantire livelli ottimali di prestazioni e archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0db8f-270">You can always accept the default mappings, which are reliable but may not provide optimal performance and storage.</span></span>  
  
 <span data-ttu-id="0db8f-271">Alcuni hint di ottimizzazione, ad esempio l'hint SINGLETON, introducono vincoli sui dati.</span><span class="sxs-lookup"><span data-stu-id="0db8f-271">Some optimization hints - for example, the SINGLETON hint - introduce constraints over your data.</span></span> <span data-ttu-id="0db8f-272">In alcuni casi, potrebbero verificarsi errori se non si rispettano tali vincoli.</span><span class="sxs-lookup"><span data-stu-id="0db8f-272">In some cases, errors may be raised when those constraints are not met.</span></span>  
  
### <a name="benefits-of-optimization-hints"></a><span data-ttu-id="0db8f-273">Vantaggi degli hint di ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="0db8f-273">Benefits of Optimization Hints</span></span>  
 <span data-ttu-id="0db8f-274">Nella tabella seguente vengono identificati gli hint di ottimizzazione che supportano livelli più efficienti di prestazioni e archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0db8f-274">The following table identifies the optimization hints that support more efficient storage or improved performance.</span></span>  
  
|<span data-ttu-id="0db8f-275">Hint di ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="0db8f-275">Optimization hint</span></span>|<span data-ttu-id="0db8f-276">Archiviazione più efficiente</span><span class="sxs-lookup"><span data-stu-id="0db8f-276">More efficient storage</span></span>|<span data-ttu-id="0db8f-277">prestazioni migliorate</span><span class="sxs-lookup"><span data-stu-id="0db8f-277">Improved performance</span></span>|  
|-----------------------|----------------------------|--------------------------|  
|<span data-ttu-id="0db8f-278">**node()**</span><span class="sxs-lookup"><span data-stu-id="0db8f-278">**node()**</span></span>|<span data-ttu-id="0db8f-279">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-279">Yes</span></span>|<span data-ttu-id="0db8f-280">No</span><span class="sxs-lookup"><span data-stu-id="0db8f-280">No</span></span>|  
|<span data-ttu-id="0db8f-281">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="0db8f-281">**SINGLETON**</span></span>|<span data-ttu-id="0db8f-282">No</span><span class="sxs-lookup"><span data-stu-id="0db8f-282">No</span></span>|<span data-ttu-id="0db8f-283">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-283">Yes</span></span>|  
|<span data-ttu-id="0db8f-284">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="0db8f-284">**DATA TYPE**</span></span>|<span data-ttu-id="0db8f-285">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-285">Yes</span></span>|<span data-ttu-id="0db8f-286">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-286">Yes</span></span>|  
|<span data-ttu-id="0db8f-287">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="0db8f-287">**MAXLENGTH**</span></span>|<span data-ttu-id="0db8f-288">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-288">Yes</span></span>|<span data-ttu-id="0db8f-289">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-289">Yes</span></span>|  
  
### <a name="optimization-hints-and-data-types"></a><span data-ttu-id="0db8f-290">Hint di ottimizzazione e tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0db8f-290">Optimization Hints and Data Types</span></span>  
 <span data-ttu-id="0db8f-291">È possibile indicizzare nodi come tipi di dati XQuery o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0db8f-291">You can index nodes as XQuery data types or as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="0db8f-292">Nella tabella seguente vengono illustrati gli hint di ottimizzazione supportati da ogni tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="0db8f-292">The following table shows which optimization hints are supported with each data type.</span></span>  
  
|<span data-ttu-id="0db8f-293">Hint di ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="0db8f-293">Optimization hint</span></span>|<span data-ttu-id="0db8f-294">Tipi di dati XQuery</span><span class="sxs-lookup"><span data-stu-id="0db8f-294">XQuery data types</span></span>|<span data-ttu-id="0db8f-295">Tipi di dati SQL</span><span class="sxs-lookup"><span data-stu-id="0db8f-295">SQL data types</span></span>|  
|-----------------------|-----------------------|--------------------|  
|<span data-ttu-id="0db8f-296">**node()**</span><span class="sxs-lookup"><span data-stu-id="0db8f-296">**node()**</span></span>|<span data-ttu-id="0db8f-297">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-297">Yes</span></span>|<span data-ttu-id="0db8f-298">No</span><span class="sxs-lookup"><span data-stu-id="0db8f-298">No</span></span>|  
|<span data-ttu-id="0db8f-299">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="0db8f-299">**SINGLETON**</span></span>|<span data-ttu-id="0db8f-300">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-300">Yes</span></span>|<span data-ttu-id="0db8f-301">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-301">Yes</span></span>|  
|<span data-ttu-id="0db8f-302">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="0db8f-302">**DATA TYPE**</span></span>|<span data-ttu-id="0db8f-303">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-303">Yes</span></span>|<span data-ttu-id="0db8f-304">No</span><span class="sxs-lookup"><span data-stu-id="0db8f-304">No</span></span>|  
|<span data-ttu-id="0db8f-305">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="0db8f-305">**MAXLENGTH**</span></span>|<span data-ttu-id="0db8f-306">Sì</span><span class="sxs-lookup"><span data-stu-id="0db8f-306">Yes</span></span>|<span data-ttu-id="0db8f-307">No</span><span class="sxs-lookup"><span data-stu-id="0db8f-307">No</span></span>|  
  
### <a name="node-optimization-hint"></a><span data-ttu-id="0db8f-308">hint di ottimizzazione node()</span><span class="sxs-lookup"><span data-stu-id="0db8f-308">node() optimization hint</span></span>  
 <span data-ttu-id="0db8f-309">Si applica a: Tipi di dati XQuery</span><span class="sxs-lookup"><span data-stu-id="0db8f-309">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="0db8f-310">È possibile utilizzare l'ottimizzazione node() per specificare un nodo il cui valore non è necessario per valutare la query tipica.</span><span class="sxs-lookup"><span data-stu-id="0db8f-310">You can use the node() optimization to specify a node whose value is not required to evaluate the typical query.</span></span> <span data-ttu-id="0db8f-311">Questo hint riduce i requisiti di archiviazione se la query tipica deve esclusivamente valutare l'esistenza del nodo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-311">This hint reduces storage requirements when the typical query only has to evaluate the existence of the node.</span></span> <span data-ttu-id="0db8f-312">Per impostazione predefinita, un indice XML selettivo archivia il valore per tutti i nodi promossi, ad eccezione dei tipi di nodi complessi.</span><span class="sxs-lookup"><span data-stu-id="0db8f-312">(By default, a selective XML index stores the value for all promoted nodes, except complex node types.)</span></span>  
  
 <span data-ttu-id="0db8f-313">Prendere in considerazione gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0db8f-313">Consider the following example:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b[./c=5]') = 1  
```  
  
 <span data-ttu-id="0db8f-314">Per utilizzare un indice XML selettivo per valutare la query, promuovere i nodi `b` e `c`.</span><span class="sxs-lookup"><span data-stu-id="0db8f-314">To use a selective XML index to evaluate this query, promote nodes `b` and `c`.</span></span> <span data-ttu-id="0db8f-315">Tuttavia, poiché il valore del nodo `b` non è necessario, è possibile utilizzare l'hint node() con la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0db8f-315">However, since the value of node `b` is not required, you can use the node() hint with the following syntax:</span></span>  
  
 `/a/b/ as node()`  
  
 <span data-ttu-id="0db8f-316">Se una query richiede il valore di un nodo indicizzato con l'hint node(), non è possibile utilizzare l'indice XML selettivo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-316">If a query requires the value of a node that has been indexed with the node() hint, then the selective XML index cannot be used.</span></span>  
  
### <a name="singleton-optimization-hint"></a><span data-ttu-id="0db8f-317">Hint di ottimizzazione SINGLETON</span><span class="sxs-lookup"><span data-stu-id="0db8f-317">SINGLETON optimization hint</span></span>  
 <span data-ttu-id="0db8f-318">Si applica a: tipi di dati XQuery o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0db8f-318">Applies to: XQuery or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types</span></span>  
  
 <span data-ttu-id="0db8f-319">L'hint di ottimizzazione SINGLETON specifica la cardinalità di un nodo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-319">The SINGLETON optimization hint specifies the cardinality of a node.</span></span> <span data-ttu-id="0db8f-320">Questo hint migliora le prestazioni delle query, poiché è risaputo che un nodo viene visualizzato al massimo una volta nel relativo elemento padre o predecessore.</span><span class="sxs-lookup"><span data-stu-id="0db8f-320">This hint improves query performance since it is known in advance that a node appears at most one time within its parent or ancestor.</span></span>  
  
 <span data-ttu-id="0db8f-321">Si consideri il [documento XML di esempio](#sample) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0db8f-321">Consider the [sample XML document](#sample) in this topic.</span></span>  
  
 <span data-ttu-id="0db8f-322">Per utilizzare un indice XML selettivo per eseguire una query sul documento, è possibile specificare l'hint SINGLETON per il nodo `d` , poiché viene visualizzato al massimo una volta all'interno del relativo padre.</span><span class="sxs-lookup"><span data-stu-id="0db8f-322">To use a selective XML index to query this document, you can specify the SINGLETON hint for node `d` since it appears at most one time within its parent.</span></span>  
  
 <span data-ttu-id="0db8f-323">Se è stato specificato l'hint SINGLETON ma un nodo viene visualizzato più di una volta nell'elemento padre o predecessore, viene generato un errore in fase di creazione dell'indice (per i dati esistenti) oppure in fase di esecuzione di una query (per i nuovi dati).</span><span class="sxs-lookup"><span data-stu-id="0db8f-323">If the SINGLETON hint has been specified, but a node appears more than one time within its parent or ancestor, then an error is raised when you create the index (for existing data) or when you run a query (for new data).</span></span>  
  
### <a name="data-type-optimization-hint"></a><span data-ttu-id="0db8f-324">Hint di ottimizzazione DATA TYPE</span><span class="sxs-lookup"><span data-stu-id="0db8f-324">DATA TYPE optimization hint</span></span>  
 <span data-ttu-id="0db8f-325">Si applica a: Tipi di dati XQuery</span><span class="sxs-lookup"><span data-stu-id="0db8f-325">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="0db8f-326">L'hint di ottimizzazione DATA TYPE consente di specificare un tipo di dati XQuery o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per il nodo indicizzato.</span><span class="sxs-lookup"><span data-stu-id="0db8f-326">The DATA TYPE optimization hint lets you specify an XQuery or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for the indexed node.</span></span> <span data-ttu-id="0db8f-327">Il tipo di dati viene utilizzato per la colonna nella tabella dati dell'indice XML selettivo che corrisponde al nodo indicizzato.</span><span class="sxs-lookup"><span data-stu-id="0db8f-327">The data type is used for the column in the data table of the selective XML index that corresponds to the indexed node.</span></span>  
  
 <span data-ttu-id="0db8f-328">Se l'esecuzione del cast di un valore esistente al tipo di dati specificato ha esito negativo, l'operazione di inserimento (nell'indice) ha esito positivo, ma viene inserito un valore Null nella tabella dati dell'indice.</span><span class="sxs-lookup"><span data-stu-id="0db8f-328">When casting an existing value to the specified data type fails, the insert operation (into the index) does not fail; however, a null value is inserted into the data table of the index.</span></span>  
  
### <a name="maxlength-optimization-hint"></a><span data-ttu-id="0db8f-329">Hint di ottimizzazione MAXLENGTH</span><span class="sxs-lookup"><span data-stu-id="0db8f-329">MAXLENGTH optimization hint</span></span>  
 <span data-ttu-id="0db8f-330">Si applica a: Tipi di dati XQuery</span><span class="sxs-lookup"><span data-stu-id="0db8f-330">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="0db8f-331">L'hint di ottimizzazione MAXLENGTH consente di limitare la lunghezza dei dati di tipo xs:string.</span><span class="sxs-lookup"><span data-stu-id="0db8f-331">The MAXLENGTH optimization hint lets you limit the length of xs:string data.</span></span> <span data-ttu-id="0db8f-332">MAXLENGTH non è rilevante per i tipi di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , poiché la lunghezza viene specificata contestualmente ai tipi di dati VARCHAR o NVARCHAR.</span><span class="sxs-lookup"><span data-stu-id="0db8f-332">MAXLENGTH is not relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types since you specify the length when you specify the VARCHAR or NVARCHAR date types.</span></span>  
  
 <span data-ttu-id="0db8f-333">Se una stringa esistente è maggiore del valore MAXLENGTH specificato, l'inserimento di tale valore nell'indice ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0db8f-333">When an existing string is longer than the specified MAXLENGTH, then inserting that value into the index fails.</span></span>  
  

  
##  <a name="sample-xml-document-for-examples"></a><a name="sample"></a> <span data-ttu-id="0db8f-334">Documento XML di esempio</span><span class="sxs-lookup"><span data-stu-id="0db8f-334">Sample XML Document for Examples</span></span>  
 <span data-ttu-id="0db8f-335">Negli esempi in questo argomento viene fatto riferimento al documento XML di esempio indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0db8f-335">The following sample XML document is referenced in the examples in this topic:</span></span>  
  
```xml  
<a>  
    <b>  
         <c atc="aa">10</c>  
         <c atc="bb">15</c>  
         <d atd1="dd" atd2="ddd">md </d>  
    </b>  
     <b>  
        <c></c>  
        <c atc="">117</c>  
     </b>  
</a>  
```  
  

  
## <a name="see-also"></a><span data-ttu-id="0db8f-336">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0db8f-336">See Also</span></span>  
 <span data-ttu-id="0db8f-337">[Indici XML selettivi &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span><span class="sxs-lookup"><span data-stu-id="0db8f-337">[Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span></span>  
 [<span data-ttu-id="0db8f-338">Creare, modificare o eliminare indici XML selettivi</span><span class="sxs-lookup"><span data-stu-id="0db8f-338">Create, Alter, and Drop Selective XML Indexes</span></span>](../xml/create-alter-and-drop-selective-xml-indexes.md)  
  
  
