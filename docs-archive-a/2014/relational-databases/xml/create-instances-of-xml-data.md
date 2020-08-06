---
title: Creare istanze di dati XML | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- type casting string instances [XML in SQL Server]
- XML [SQL Server], typed
- xml data type [SQL Server], generating instances
- casting string instances [XML in SQL Server]
- typed XML
- generating XML instances [SQL Server]
- XML [SQL Server], generating instances
- white space [XML in SQL Server]
ms.assetid: dbd6c06f-db6e-44a7-855a-6a55bf374907
author: rothja
ms.author: jroth
ms.openlocfilehash: c857b9ebbe559de34fdac925642f9270d9cbf936
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726795"
---
# <a name="create-instances-of-xml-data"></a><span data-ttu-id="830e4-102">Creare istanze di dati XML</span><span class="sxs-lookup"><span data-stu-id="830e4-102">Create Instances of XML Data</span></span>
  <span data-ttu-id="830e4-103">In questo argomento viene descritto come generare istanze XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-103">This topic describes how to generate XML instances.</span></span>  
  
 <span data-ttu-id="830e4-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]è possibile generare istanze XML tramite i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="830e4-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can generate XML instances in the following ways:</span></span>  
  
-   <span data-ttu-id="830e4-105">Cast dei tipi delle istanze di dati di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="830e4-105">Type casting string instances.</span></span>  
  
-   <span data-ttu-id="830e4-106">Utilizzo dell'istruzione SELECT con la clausola FOR XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-106">Using the SELECT statement with the FOR XML clause.</span></span>  
  
-   <span data-ttu-id="830e4-107">Utilizzo di assegnazioni di costanti.</span><span class="sxs-lookup"><span data-stu-id="830e4-107">Using constant assignments.</span></span>  
  
-   <span data-ttu-id="830e4-108">Utilizzo del caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="830e4-108">Using bulk load.</span></span>  
  
## <a name="type-casting-string-and-binary-instances"></a><span data-ttu-id="830e4-109">Cast di tipo di istanze binarie e di stringa</span><span class="sxs-lookup"><span data-stu-id="830e4-109">Type Casting String and Binary Instances</span></span>  
 <span data-ttu-id="830e4-110">È possibile analizzare qualsiasi tipo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dati stringa, ad esempio [**n**] [**var**]**char**, **[n] text**, **varbinary**e **Image**, nel `xml` tipo di dati eseguendo il cast (cast) o convertendo (converte) la stringa nel `xml` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="830e4-110">You can parse any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] string data types, such as [**n**][**var**]**char**, **[n]text**, **varbinary**,and **image**, into the `xml` data type by casting (CAST) or converting (CONVERT) the string to the `xml` data type.</span></span> <span data-ttu-id="830e4-111">L'istanza XML non tipizzata viene controllata per verificare che il formato sia corretto.</span><span class="sxs-lookup"><span data-stu-id="830e4-111">Untyped XML is checked to confirm that it is well formed.</span></span> <span data-ttu-id="830e4-112">Se al tipo è associato uno schema `xml` , viene anche eseguita la convalida.</span><span class="sxs-lookup"><span data-stu-id="830e4-112">If there is a schema associated with the `xml` type, validation is also performed.</span></span> <span data-ttu-id="830e4-113">Per altre informazioni, vedere [Confrontare dati XML tipizzati con dati XML non tipizzati](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="830e4-113">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
 <span data-ttu-id="830e4-114">I documenti XML possono essere codificati con codifiche diverse, ad esempio UTF-8, UTF-16, windows-1252).</span><span class="sxs-lookup"><span data-stu-id="830e4-114">XML documents can be encoded with different encodings (for example, UTF-8, UTF-16, windows-1252).</span></span> <span data-ttu-id="830e4-115">Di seguito vengono descritte le regole in base alle quali i tipi di origine di stringa e binari interagiscono con la codifica del documento XML, nonché il comportamento del parser.</span><span class="sxs-lookup"><span data-stu-id="830e4-115">The following outlines the rules on how the string and binary source types interact with the XML document encoding and how the parser behaves.</span></span>  
  
 <span data-ttu-id="830e4-116">Dato che **nvarchar** presuppone una codifica unicode a 2 byte come UTF-16 o UCS-2, il parser XML tratterà il valore stringa come un documento o frammento XML codificato Unicode a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="830e4-116">Since **nvarchar** assumes a two-byte unicode encoding such as UTF-16 or UCS-2, the XML parser will treat the string value as a two-byte Unicode encoded XML document or fragment.</span></span> <span data-ttu-id="830e4-117">Questo significa che anche il documento XML dovrà essere codificato tramite codifica Unicode a 2 byte per essere compatibile con il tipo di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="830e4-117">This means that the XML document needs to be encoded in a two-byte Unicode encoding as well to be compatible with the source data type.</span></span> <span data-ttu-id="830e4-118">Un documento XML con codifica UTF-16 potrà, ma non dovrà obbligatoriamente, includere un indicatore dell'ordine dei byte (BOM) UTF-16, in quanto il contesto del tipo di origine chiarisce che può trattarsi solo di un documento con codifica Unicode a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="830e4-118">A UTF-16 encoded XML document can have a UTF-16 byte order mark (BOM), but it does not need to, since the context of the source type makes it clear that it can only be a two-byte Unicode encoded document.</span></span>  
  
 <span data-ttu-id="830e4-119">Il contenuto di una stringa **varchar** viene trattato come documento/frammento XML con codifica a 1 byte da parte del parser XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-119">The content of a **varchar** string is treated as a one-byte encoded XML document/fragment by the XML parser.</span></span> <span data-ttu-id="830e4-120">Dato che alla stringa di origine **varchar** è associata una tabella codici, il parser la utilizzerà per la codifica se non nel documento XML non viene specificata alcuna codifica. Se un'istanza XML include un BOM o una dichiarazione di codifica, quest'ultima deve essere consistente con la tabella codici, altrimenti il parser genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="830e4-120">Since the **varchar** source string has a code page associated, the parser will use that code page for the encoding if no explicit encoding is specified in the XML itself If an XML instance has a BOM or an encoding declaration, the BOM or declaration needs to be consistent with the code page, otherwise the parser will report an error.</span></span>  
  
 <span data-ttu-id="830e4-121">Il contenuto di **varbinary** viene trattato come flusso di punti di codice passato direttamente al parser XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-121">The content of **varbinary** is treated as a codepoint stream that is passed directly to the XML parser.</span></span> <span data-ttu-id="830e4-122">Di conseguenza, il documento o frammento XML deve specificare il BOM o altra informazione sulla codifica inline.</span><span class="sxs-lookup"><span data-stu-id="830e4-122">Thus, the XML document or fragment needs to provide the BOM or other encoding information inline.</span></span> <span data-ttu-id="830e4-123">Il parser esaminerà solo il flusso per determinare la codifica.</span><span class="sxs-lookup"><span data-stu-id="830e4-123">The parser will only look at the stream to determine the encoding.</span></span> <span data-ttu-id="830e4-124">Questo significa che il documento XML con codifica UTF-16 deve specificare il BOM UTF-16 e che un'istanza senza BOM e senza dichiarazione di codifica verrà interpretata come UTF-8.</span><span class="sxs-lookup"><span data-stu-id="830e4-124">This means that UTF-16 encoded XML needs to provide the UTF-16 BOM and an instance without BOM and without a declaration encoding will be interpreted as UTF-8.</span></span>  
  
 <span data-ttu-id="830e4-125">Se la codifica del documento XML non è già nota e i dati vengono passati dati di tipo stringa o binari anziché come dati XML prima che venga eseguito il cast sull'XML, è consigliabile trattare i dati come **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="830e4-125">If the encoding of the XML document is not known in advance and the data is passed as string or binary data instead of XML data before casting to XML, it is recommended to treat the data as **varbinary**.</span></span> <span data-ttu-id="830e4-126">Ad esempio, nella lettura dei dati da un file XML utilizzando OpenRowset(), specificare i dati da leggere come valore **varbinary(max)** :</span><span class="sxs-lookup"><span data-stu-id="830e4-126">For example, when reading data from an XML file using OpenRowset(), one should specify the data to be read as a **varbinary(max)** value:</span></span>  
  
```  
select CAST(x as XML)   
from OpenRowset(BULK 'filename.xml', SINGLE_BLOB) R(x)  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="830e4-127">offre internamente una rappresentazione binaria efficiente dell'istanza XML, basata sulla codifica UTF-16.</span><span class="sxs-lookup"><span data-stu-id="830e4-127">internally represents XML in an efficient binary representation that uses UTF-16 encoding.</span></span> <span data-ttu-id="830e4-128">La codifica specificata dall'utente non viene mantenuta, ma viene considerata durante il processo di analisi.</span><span class="sxs-lookup"><span data-stu-id="830e4-128">User-provided encoding is not preserved, but is considered during the parse process.</span></span>  
  
### <a name="type-casting-clr-user-defined-types"></a><span data-ttu-id="830e4-129">Cast di tipo di tipi CLR definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="830e4-129">Type Casting CLR user-defined types</span></span>  
 <span data-ttu-id="830e4-130">Se un tipo CLR definito dall'utente include una serializzazione XML, per le istanze di tale tipo è possibile eseguire il cast in modo esplicito su un tipo di dati XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-130">If a CLR user-defined type has an XML Serialization, instances of that type can be explicitly cast to an XML datatype.</span></span> <span data-ttu-id="830e4-131">Per altri dettagli sulla serializzazione XML di un tipo CLR definito dall'utente, vedere [Serializzazione XML da oggetti di database CLR](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="830e4-131">For more details about the XML serialization of a CLR user-defined typed, see [XML Serialization from CLR Database Objects](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span></span>  
  
### <a name="white-space-handling-in-typed-xml"></a><span data-ttu-id="830e4-132">Gestione degli spazi vuoti nell'istanza XML tipizzata</span><span class="sxs-lookup"><span data-stu-id="830e4-132">White Space Handling in Typed XML</span></span>  
 <span data-ttu-id="830e4-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], gli spazi vuoti all'interno del contenuto degli elementi vengono considerati non significativi se ricorrono in una sequenza di dati di tipo carattere composti solo da spazi vuoti delimitati da markup, ad esempio tag di inizio e di fine, e non vengono sostituiti con entità.</span><span class="sxs-lookup"><span data-stu-id="830e4-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], white space inside element content is considered insignificant if it occurs inside a sequence of white-space-only character data delimited by markup, such as begin or end tags, and is not entitized.</span></span> <span data-ttu-id="830e4-134">Le sezioni CDATA vengono ignorate. Questa modalità di gestione degli spazi vuoti è diversa da quella descritta nella specifica XML 1.0 pubblicata dal World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="830e4-134">(CDATA sections are ignored.) This handling of white space handling is different from how white space is described in the XML 1.0 specification published by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="830e4-135">Tale differenza è dovuta al fatto che il parser XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] riconosce solo un numero limitato di subset DTD, come definito nella specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="830e4-135">This is because the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recognizes only a limited number of DTD subsets, as defined in XML 1.0.</span></span> <span data-ttu-id="830e4-136">Per altre informazioni sul numero limitato di subset DTD supportati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [CAST e CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="830e4-136">For more information about the limited DTD subsets supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
 <span data-ttu-id="830e4-137">Per impostazione predefinita, il parser XML elimina gli spazi vuoti durante la conversione di dati di tipo stringa nel formato XML in uno dei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="830e4-137">By default, the XML parser discards insignificant white space when it converts string data to XML if either of the following is true:</span></span>  
  
-   <span data-ttu-id="830e4-138">`The xml:space` l'attributo non viene definito per un elemento o i relativi predecessori.</span><span class="sxs-lookup"><span data-stu-id="830e4-138">`The xml:space` attribute is not defined on an element or its ancestor elements.</span></span>  
  
-   <span data-ttu-id="830e4-139">Viene assegnato il valore predefinito all'attributo `xml:space` attivo per un elemento o i relativi predecessori.</span><span class="sxs-lookup"><span data-stu-id="830e4-139">The `xml:space` attribute in effect on an element, or one of its ancestor elements, has the value of default.</span></span>  
  
 <span data-ttu-id="830e4-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="830e4-140">For example:</span></span>  
  
```  
declare @x xml  
set @x = '<root>      <child/>     </root>'  
select @x   
```  
  
 <span data-ttu-id="830e4-141">Risultato:</span><span class="sxs-lookup"><span data-stu-id="830e4-141">This is the result:</span></span>  
  
```  
<root><child/></root>  
```  
  
 <span data-ttu-id="830e4-142">È tuttavia possibile modificare tale impostazione.</span><span class="sxs-lookup"><span data-stu-id="830e4-142">However, you can change this behavior.</span></span> <span data-ttu-id="830e4-143">Per mantenere gli spazi vuoti in un'istanza XML DT, è possibile utilizzare l'operatore CONVERT e il parametro facoltativo *style* corrispondente impostato sul valore 1.</span><span class="sxs-lookup"><span data-stu-id="830e4-143">To preserve white space for an xml DT instance, use the CONVERT operator and its optional *style* parameter set to a value of 1.</span></span> <span data-ttu-id="830e4-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="830e4-144">For example:</span></span>  
  
```  
SELECT CONVERT(xml, N'<root>      <child/>     </root>', 1)  
```  
  
 <span data-ttu-id="830e4-145">Se il parametro *style* non viene utilizzato o è impostato sul valore 0, gli spazi vuoti non significativi non vengono mantenuti per la conversione dell'istanza XML DT.</span><span class="sxs-lookup"><span data-stu-id="830e4-145">If the *style* parameter is either not used or its value is set to 0, insignificant white space is not preserved for the conversion of the xml DT instance.</span></span> <span data-ttu-id="830e4-146">Per altre informazioni sull'uso dell'operatore CONVERT e del parametro *style* durante la conversione di dati di tipo stringa in istanze XML DT, vedere [CAST e CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="830e4-146">For more information about how to use the CONVERT operator and its *style* parameter when converting string data to xml DT instances, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
### <a name="example-cast-a-string-value-to-typed-xml-and-assign-it-to-a-column"></a><span data-ttu-id="830e4-147">Esempio: Eseguire il cast di un valore stringa al tipo XML tipizzato e assegnarlo a una colonna</span><span class="sxs-lookup"><span data-stu-id="830e4-147">Example: Cast a string value to typed xml and assign it to a column</span></span>  
 <span data-ttu-id="830e4-148">Nell'esempio seguente viene eseguito il cast di una variabile stringa che contiene un frammento XML al `xml` tipo di dati e quindi la archivia nella `xml` colonna Type:</span><span class="sxs-lookup"><span data-stu-id="830e4-148">The following example casts a string variable that contains an XML fragment to the `xml` data type and then stores it in the `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
go  
DECLARE  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
```  
  
 <span data-ttu-id="830e4-149">L'operazione di inserimento seguente converte in modo implicito una stringa nel `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="830e4-149">The following insert operation implicitly converts from a string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, @s)   
```  
  
 <span data-ttu-id="830e4-150">È possibile eseguire il cast esplicito () della stringa al `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="830e4-150">You can explicitly cast() the string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, cast (@s as xml))  
```  
  
 <span data-ttu-id="830e4-151">In alternativa, è possibile utilizzare convert(), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="830e4-151">Or you can use convert(), as shown in the following:</span></span>  
  
```  
INSERT INTO T VALUES (3, convert (xml, @s))   
```  
  
### <a name="example-convert-a-string-to-typed-xml-and-assign-it-to-a-variable"></a><span data-ttu-id="830e4-152">Esempio: Convertire una stringa nel tipo XML tipizzato e assegnarla a una variabile</span><span class="sxs-lookup"><span data-stu-id="830e4-152">Example: Convert a string to typed xml and assign it to a variable</span></span>  
 <span data-ttu-id="830e4-153">Nell'esempio seguente, una stringa viene convertita nel `xml` tipo e assegnata a una variabile del `xml` tipo di dati:</span><span class="sxs-lookup"><span data-stu-id="830e4-153">In the following example, a string is converted to `xml` type and assigned to a variable of the `xml` data type:</span></span>  
  
```  
declare @x xml  
declare  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
set @x =convert (xml, @s)  
select @x  
```  
  
## <a name="using-the-select-statement-with-a-for-xml-clause"></a><span data-ttu-id="830e4-154">Utilizzo dell'istruzione SELECT con la clausola FOR XML</span><span class="sxs-lookup"><span data-stu-id="830e4-154">Using the SELECT Statement with a FOR XML Clause</span></span>  
 <span data-ttu-id="830e4-155">È possibile utilizzare la clausola FOR XML in un'istruzione SELECT per restituire i risultati in formato XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-155">You can use the FOR XML clause in a SELECT statement to return results as XML.</span></span> <span data-ttu-id="830e4-156">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="830e4-156">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = (SELECT Column1, Column2  
               FROM   Table1, Table2  
               WHERE   Some condition  
               FOR XML AUTO)  
 ...  
```  
  
 <span data-ttu-id="830e4-157">L'istruzione SELECT restituisce un frammento XML testuale che viene quindi analizzato durante l'assegnazione alla `xml` variabile del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="830e4-157">The SELECT statement returns a textual XML fragment that is then parsed during the assignment to the `xml` data type variable.</span></span>  
  
 <span data-ttu-id="830e4-158">Nella clausola FOR XML è inoltre possibile utilizzare la [direttiva Type](type-directive-in-for-xml-queries.md) che restituisce direttamente il risultato di una query for XML come `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="830e4-158">You can also use the [TYPE directive](type-directive-in-for-xml-queries.md) in the FOR XML clause that directly returns a FOR XML query result as `xml` type:</span></span>  
  
```  
Declare @xmlDoc xml  
SET @xmlDoc = (SELECT ProductModelID, Name  
               FROM   Production.ProductModel  
               WHERE  ProductModelID=19  
               FOR XML AUTO, TYPE)  
SELECT @xmlDoc  
```  
  
 <span data-ttu-id="830e4-159">Risultato:</span><span class="sxs-lookup"><span data-stu-id="830e4-159">This is the result:</span></span>  
  
```  
<Production.ProductModel ProductModelID="19" Name="Mountain-100" />...  
```  
  
 <span data-ttu-id="830e4-160">Nell'esempio seguente, il risultato tipizzato `xml` di una query for XML viene inserito in una `xml` colonna di tipo:</span><span class="sxs-lookup"><span data-stu-id="830e4-160">In the following example, the typed `xml` result of a FOR XML query is inserted into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T1 (c1 int, c2 xml)  
go  
INSERT T1(c1, c2)  
SELECT 1, (SELECT ProductModelID, Name  
           FROM Production.ProductModel  
           WHERE ProductModelID=19  
           FOR XML AUTO, TYPE)  
SELECT * FROM T1  
go  
```  
  
 <span data-ttu-id="830e4-161">Per altre informazioni su FOR XML, vedere [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="830e4-161">For more information about FOR XML, see [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="830e4-162">consente di restituire al client istanze con tipo di dati `xml` come risultato di diversi costrutti server, quali query FOR XML che utilizzano la direttiva TYPE, o nel caso in cui il tipo di dati `xml` venga utilizzato per restituire il codice XML da colonne SQL, variabili o parametri di output.</span><span class="sxs-lookup"><span data-stu-id="830e4-162">returns `xml` data type instances to the client as a result of different server constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML from SQL columns, variables, and output parameters.</span></span> <span data-ttu-id="830e4-163">Nel codice dell'applicazione client il provider ADO.NET richiede che queste informazioni con tipo di dati `xml` siano inviate dal server utilizzando una codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="830e4-163">In client application code, the ADO.NET provider requests that this `xml` data type information be sent in a binary encoding from the server.</span></span> <span data-ttu-id="830e4-164">Se tuttavia si utilizza FOR XML senza la direttiva TYPE, i dati XML vengono restituiti come tipo string.</span><span class="sxs-lookup"><span data-stu-id="830e4-164">However, if you are using FOR XML without the TYPE directive, the XML data returns as a string type.</span></span> <span data-ttu-id="830e4-165">In tutti i casi, il provider client sarà sempre in grado di gestire entrambe i formati di XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-165">In any case, the client provider will always be able to handle either form of XML.</span></span>  
  
## <a name="using-constant-assignments"></a><span data-ttu-id="830e4-166">Utilizzo di assegnazioni di costanti</span><span class="sxs-lookup"><span data-stu-id="830e4-166">Using Constant Assignments</span></span>  
 <span data-ttu-id="830e4-167">È possibile utilizzare una costante stringa in cui è prevista un'istanza del `xml` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="830e4-167">A string constant can be used where an instance of the `xml` data type is expected.</span></span> <span data-ttu-id="830e4-168">Tale operazione è equivalente a un CAST implicito della stringa al formato XML.</span><span class="sxs-lookup"><span data-stu-id="830e4-168">This is the same as an implied CAST of string to XML.</span></span> <span data-ttu-id="830e4-169">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="830e4-169">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
-- Or  
SET @xmlDoc = N'<?xml version="1.0" encoding="ucs-2"?><doc/>'  
```  
  
 <span data-ttu-id="830e4-170">Nell'esempio precedente la stringa viene convertita in modo implicito nel `xml` tipo di dati e assegnata a una `xml` variabile di tipo.</span><span class="sxs-lookup"><span data-stu-id="830e4-170">The previous example implicitly converts the string to the `xml` data type and assigns it to an `xml` type variable.</span></span>  
  
 <span data-ttu-id="830e4-171">Nell'esempio seguente viene inserita una stringa costante in una `xml` colonna di tipo:</span><span class="sxs-lookup"><span data-stu-id="830e4-171">The following example inserts a constant string into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
INSERT INTO T VALUES (3, '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>')   
```  
  
> [!NOTE]  
>  <span data-ttu-id="830e4-172">L'istanza XML tipizzata viene convalidata in base allo schema specificato.</span><span class="sxs-lookup"><span data-stu-id="830e4-172">For typed XML, the XML is validated against the specified schema.</span></span> <span data-ttu-id="830e4-173">Per altre informazioni, vedere [Confrontare dati XML tipizzati con dati XML non tipizzati](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="830e4-173">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
## <a name="using-bulk-load"></a><span data-ttu-id="830e4-174">Utilizzo del caricamento bulk</span><span class="sxs-lookup"><span data-stu-id="830e4-174">Using Bulk Load</span></span>  
 <span data-ttu-id="830e4-175">La funzionalità avanzata [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) consente di eseguire il caricamento bulk dei documenti XML nel database.</span><span class="sxs-lookup"><span data-stu-id="830e4-175">The enhanced [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) functionality allows you to bulk load XML documents in the database.</span></span> <span data-ttu-id="830e4-176">È possibile eseguire il caricamento bulk delle istanze XML dai file nelle `xml` colonne di tipo del database.</span><span class="sxs-lookup"><span data-stu-id="830e4-176">You can bulk load XML instances from files into the `xml` type columns in the database.</span></span> <span data-ttu-id="830e4-177">Per esempi funzionanti, vedere [Esempi di importazione ed esportazione bulk di documenti XML &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="830e4-177">For working samples, see [Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span></span> <span data-ttu-id="830e4-178">Per altre informazioni sul caricamento dei documenti XML, vedere [Caricare dati XML](load-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="830e4-178">For more information about loading XML documents, see [Load XML Data](load-xml-data.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="830e4-179">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="830e4-179">In This Section</span></span>  
  
|<span data-ttu-id="830e4-180">Argomento</span><span class="sxs-lookup"><span data-stu-id="830e4-180">Topic</span></span>|<span data-ttu-id="830e4-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="830e4-181">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="830e4-182">Recuperare ed eseguire query su dati XML</span><span class="sxs-lookup"><span data-stu-id="830e4-182">Retrieve and Query XML Data</span></span>](retrieve-and-query-xml-data.md)|<span data-ttu-id="830e4-183">Descrizione delle parti di istanze XML che non sono mantenute quando vengono archiviate nei database.</span><span class="sxs-lookup"><span data-stu-id="830e4-183">Describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="830e4-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="830e4-184">See Also</span></span>  
 <span data-ttu-id="830e4-185">[Confronto dati XML tipizzati con dati XML non tipizzati](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="830e4-185">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="830e4-186">[metodi con tipo di dati XML](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="830e4-186">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="830e4-187">[Linguaggio XML di manipolazione dei dati &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="830e4-187">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="830e4-188">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="830e4-188">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
