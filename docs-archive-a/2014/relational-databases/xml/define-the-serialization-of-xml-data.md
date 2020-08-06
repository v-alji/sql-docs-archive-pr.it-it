---
title: Definire la serializzazione di dati XML | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- entitization rules [XML in SQL Server]
- serialization
- reparsing serialized XML structures
- encoding [XML in SQL Server]
- XML [SQL Server], serialization
- xml data type [SQL Server], serialization
- typed XML
ms.assetid: 42b0b5a4-bdd6-4a60-b451-c87f14758d4b
author: rothja
ms.author: jroth
ms.openlocfilehash: df87dddd9fd4cf067125314c9d798eaa42523576
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637666"
---
# <a name="define-the-serialization-of-xml-data"></a><span data-ttu-id="ee6b0-102">Definire la serializzazione di dati XML</span><span class="sxs-lookup"><span data-stu-id="ee6b0-102">Define the Serialization of XML Data</span></span>
  <span data-ttu-id="ee6b0-103">Quando si esegue il cast esplicito o implicito del tipo di dati xml a un tipo SQL stringa o binario, il contenuto del tipo di dati xml verrà serializzato in base alle regole illustrate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-103">When casting the xml data type explicitly or implicitly to a SQL string or binary type, the content of the xml data type will be serialized according to the rules outlined in this topic.</span></span>  
  
## <a name="serialization-encoding"></a><span data-ttu-id="ee6b0-104">Codifica della serializzazione</span><span class="sxs-lookup"><span data-stu-id="ee6b0-104">Serialization Encoding</span></span>  
 <span data-ttu-id="ee6b0-105">Se il tipo SQL di destinazione è VARBINARY, il risultato viene serializzato nel formato UTF-16 preceduto da un indicatore dell'ordine dei byte UTF-16, ma senza una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-105">If the SQL target type is VARBINARY, the result is serialized in UTF-16 with a UTF-16-byte order mark in front, but without an XML declaration.</span></span> <span data-ttu-id="ee6b0-106">Se il tipo di destinazione è di grandezza troppo ridotta, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-106">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="ee6b0-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-107">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARBINARY(MAX))  
```  
  
 <span data-ttu-id="ee6b0-108">Risultato:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-108">This is the result:</span></span>  
  
```  
0xFFFE3C0094032F003E00  
```  
  
 <span data-ttu-id="ee6b0-109">Se il tipo SQL di destinazione è NVARCHAR o NCHAR, il risultato viene serializzato nel formato UTF-16 non preceduto dall'indicatore dell'ordine dei byte e senza una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-109">If the SQL target type is NVARCHAR or NCHAR, the result is serialized in UTF-16 without the byte order mark in front and without an XML declaration.</span></span> <span data-ttu-id="ee6b0-110">Se il tipo di destinazione è di grandezza troppo ridotta, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-110">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="ee6b0-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-111">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as NVARCHAR(MAX))  
```  
  
 <span data-ttu-id="ee6b0-112">Risultato:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-112">This is the result:</span></span>  
  
```  
<Δ/>  
```  
  
 <span data-ttu-id="ee6b0-113">Se il tipo SQL di destinazione è VARCHAR o NCHAR, il risultato viene serializzato nella codifica corrispondente alla tabella codici delle regole di confronto del database, senza un indicatore dell'ordine dei byte o una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-113">If the SQL target type is VARCHAR or NCHAR, the result is serialized in the encoding that corresponds to the database's collation code page without a byte order mark or XML declaration.</span></span> <span data-ttu-id="ee6b0-114">Se il tipo di destinazione è di grandezza troppo ridotta o se non è possibile eseguire il mapping del valore alla tabella codici delle regole di confronto di destinazione, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-114">If the target type is too small or the value cannot be mapped to the target collation code page, an error is raised.</span></span>  
  
 <span data-ttu-id="ee6b0-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-115">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARCHAR(MAX))  
```  
  
 <span data-ttu-id="ee6b0-116">È possibile che si verifichi un errore se la tabella codici delle regole di confronto correnti non è in grado di rappresentare il carattere Unicode & # x10300; o se viene rappresentata nella codifica specifica.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-116">This may result in an error, if the current collation's code page cannot represent the Unicode character &#x10300;, or it will represent it in the specific encoding.</span></span>  
  
 <span data-ttu-id="ee6b0-117">Per la restituzione dei risultati XML al lato client, i dati verranno inviati con la codifica UTF-16.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-117">When returning XML results to the client side, the data will be sent in UTF-16 encoding.</span></span> <span data-ttu-id="ee6b0-118">Il provider sul lato client esporrà quindi i dati in base alle regole delle relative API.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-118">The client-side provider will then expose the data according to its API rules.</span></span>  
  
## <a name="serialization-of-the-xml-structures"></a><span data-ttu-id="ee6b0-119">Serializzazione delle strutture XML</span><span class="sxs-lookup"><span data-stu-id="ee6b0-119">Serialization of the XML Structures</span></span>  
 <span data-ttu-id="ee6b0-120">Il contenuto di un tipo di dati **xml** viene serializzato nel modo standard.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-120">The content of an **xml** data type is serialized in the usual way.</span></span> <span data-ttu-id="ee6b0-121">In particolare, viene eseguito il mapping dei nodi elemento al markup dell'elemento e il mapping dei nodi di testo al contenuto testuale.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-121">Specifically, element nodes are mapped to element markup, and text nodes are mapped to text content.</span></span> <span data-ttu-id="ee6b0-122">Nelle sezioni seguenti vengono tuttavia illustrate le situazioni in cui i caratteri vengono sostituiti con entità e le modalità di serializzazione dei valori atomici tipizzati.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-122">However, the circumstances under which characters are entitized and how typed atomic values are serialized are described in the following sections.</span></span>  
  
## <a name="entitization-of-xml-characters-during-serialization"></a><span data-ttu-id="ee6b0-123">Sostituzione dei caratteri XML con entità durante la serializzazione</span><span class="sxs-lookup"><span data-stu-id="ee6b0-123">Entitization of XML Characters During Serialization</span></span>  
 <span data-ttu-id="ee6b0-124">È consigliabile analizzare tutte le strutture XML serializzate.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-124">Every serialized XML structure should be capable of being reparsed.</span></span> <span data-ttu-id="ee6b0-125">La serializzazione di alcuni caratteri deve pertanto prevedere la sostituzione con entità, in modo tale da mantenere per i caratteri la possibilità di eseguire il round trip durante la fase di normalizzazione del parser XML.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-125">Therefore, some characters have to be serialized in an entitized way to preserve the round-trip capability of the characters through the XML parser's normalization phase .</span></span> <span data-ttu-id="ee6b0-126">La sostituzione di alcuni caratteri con entità deve tuttavia garantire che il documento sia ben formato e possa pertanto essere analizzato.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-126">However, some characters have to be entitized so that the document is well-formed and, therefore, able to be parsed.</span></span> <span data-ttu-id="ee6b0-127">Di seguito sono illustrate le regole della sostituzione con entità applicabili alla serializzazione:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-127">Following are the entitization rules that apply during serialization:</span></span>  
  
-   <span data-ttu-id="ee6b0-128">I caratteri &, \<, and > vengono sempre sostituiti rispettivamente con le entità &amp;, &lt; e &gt; se sono presenti in un valore di attributo o nel contenuto di un elemento.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-128">The characters &, \<, and > are always entitized to &amp;, &lt;, and &gt; respectively, if they occur inside an attribute value or element content.</span></span>  
  
-   <span data-ttu-id="ee6b0-129">SQL Server racchiude i valori di attributo tra virgolette singole (U+0022) e pertanto la virgoletta nei valori di attributo viene sostituita con l'entità &quot;.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-129">Because SQL Server uses a quotation mark (U+0022) for enclosing attribute values, the quotation mark in attribute values is entitized as &quot;.</span></span>  
  
-   <span data-ttu-id="ee6b0-130">Una coppia di surrogati viene sostituita dall'entità rappresentata da un riferimento a un singolo carattere numerico, se il cast viene eseguito solo nel server.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-130">A surrogate pair is entitized as a single numeric character reference, when casting on the server only.</span></span> <span data-ttu-id="ee6b0-131">Ad esempio, la coppia di surrogati U+D800 U+DF00 viene sostituita dall'entità rappresentata dal riferimento al carattere numerico &\#x00010300;.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-131">For example the surrogate pair U+D800 U+DF00 is entitized to the numeric character reference &\#x00010300;.</span></span>  
  
-   <span data-ttu-id="ee6b0-132">Per evitare che una tabulazione TAB (U+0009) e un avanzamento di riga (LF, U+000A) vengano normalizzati durante l'analisi, vengono sostituiti con le entità rappresentate dai relativi riferimenti a caratteri numerici, rispettivamente &\#x9; e &\#xA;, all'interno dei valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-132">To protect a TAB (U+0009) and a linefeed (LF, U+000A) from being normalized during parsing, they are entitized to their numeric character references &\#x9; and &\#xA; respectively, inside attribute values.</span></span>  
  
-   <span data-ttu-id="ee6b0-133">Per evitare che un ritorno a capo (CR, U+000D) venga normalizzato durante l'analisi, viene sostituito con l'entità rappresentata dal relativo riferimento a un carattere numerico, &\#xD; all'interno dei valori di attributo e nel contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-133">To prevent a carriage return (CR, U+000D) from being normalized during parsing, it is entitized to its numeric character reference, &\#xD; inside both attribute values and element content.</span></span>  
  
-   <span data-ttu-id="ee6b0-134">Per proteggere i nodi di testo che contengono solo spazi vuoti, uno degli spazi vuoti (in genere l'ultimo) viene sostituito con l'entità rappresentata dal relativo riferimento a un carattere numerico.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-134">To protect text nodes that only contain white space, one of the white-space characters, generally the last one, is entitized as its numeric character reference.</span></span> <span data-ttu-id="ee6b0-135">In questo modo, durante l'analisi il nodo di testo con spazi vuoti viene mantenuto, indipendentemente da come vengono gestiti gli spazi vuoti durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-135">In this way, reparsing preserves the white-space text node, regardless of the setting of the white-space handling during parsing.</span></span>  
  
 <span data-ttu-id="ee6b0-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-136">For example:</span></span>  
  
```sql
declare @u NVARCHAR(50)  
set @u = N'<a a="  
    '+NCHAR(0xD800)+NCHAR(0xDF00)+N'>">   '+NCHAR(0xA)+N'</a>'  
select CAST(CONVERT(XML,@u,1) as NVARCHAR(50))  
```  
  
 <span data-ttu-id="ee6b0-137">Risultato:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-137">This is the result:</span></span>  
  
```  
<a a="  
    𐌀>">     
</a>  
```  
  
 <span data-ttu-id="ee6b0-138">Se non si vuole applicare l'ultima regola relativa agli spazi vuoti, è possibile usare l'opzione esplicita CONVERT 1 quando si esegue il cast dal tipo **xml** a un tipo string o binary.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-138">If you do not want to apply the last white-space protection rule, you can use the explicit CONVERT option 1 when casting from **xml** to a string or binary type.</span></span> <span data-ttu-id="ee6b0-139">Ad esempio, per evitare la sostituzione con entità, è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-139">For example, to avoid entitization, you can do the following:</span></span>  
  
```sql
select CONVERT(NVARCHAR(50), CONVERT(XML, '<a>   </a>', 1), 1)  
```  
  
 <span data-ttu-id="ee6b0-140">Si noti che il [metodo query() (tipo di dati xml)](/sql/t-sql/xml/query-method-xml-data-type) restituisce un'istanza del tipo di dati xml.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-140">Note that, the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) results in an xml data type instance.</span></span> <span data-ttu-id="ee6b0-141">Qualsiasi risultato del metodo **query()** per cui viene eseguito il cast a un tipo string o binary viene pertanto sostituito con entità in base alle regole descritte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-141">Therefore, any result of the **query()** method that is cast to a string or binary type is entitized according to the previously described rules.</span></span> <span data-ttu-id="ee6b0-142">Per evitare che i valori stringa ottenuti vengano sostituiti con entità, è consigliabile usare invece il [metodo value() (tipo di dati xml)](/sql/t-sql/xml/value-method-xml-data-type) .</span><span class="sxs-lookup"><span data-stu-id="ee6b0-142">If you want to obtain the string values that are not entitized, you should use the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) instead.</span></span> <span data-ttu-id="ee6b0-143">Di seguito è riportato un esempio d'uso del metodo **query()** :</span><span class="sxs-lookup"><span data-stu-id="ee6b0-143">Following is an example of using the **query()** method:</span></span>  
  
```sql
declare @x xml  
set @x = N'<a>This example contains an entitized char: <.</a>'  
select @x.query('/a/text()')  
```  
  
 <span data-ttu-id="ee6b0-144">Risultato:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-144">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
 <span data-ttu-id="ee6b0-145">Di seguito è riportato un esempio d'uso del metodo **value()** :</span><span class="sxs-lookup"><span data-stu-id="ee6b0-145">Following is an example of using the **value()** method:</span></span>  
  
```sql
select @x.value('(/a/text())[1]', 'nvarchar(100)')  
```  
  
 <span data-ttu-id="ee6b0-146">Risultato:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-146">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
## <a name="serializing-a-typed-xml-data-type"></a><span data-ttu-id="ee6b0-147">Serializzazione di un tipo di dati xml tipizzato</span><span class="sxs-lookup"><span data-stu-id="ee6b0-147">Serializing a Typed xml Data Type</span></span>  
 <span data-ttu-id="ee6b0-148">Un'istanza di un tipo di dati **xml** tipizzato contiene valori tipizzati in base ai relativi tipi XML Schema.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-148">A typed **xml** data type instance contains values that are typed according to their XML schema types.</span></span> <span data-ttu-id="ee6b0-149">Tali valori vengono serializzati in base al tipo XML Schema nel stesso formato generato dal cast di XQuery a xs:string.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-149">These values are serialized according to their XML schema type in the same format as the XQuery cast to xs:string produces.</span></span> <span data-ttu-id="ee6b0-150">Per altre informazioni, vedere [Regole del cast dei tipi in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span><span class="sxs-lookup"><span data-stu-id="ee6b0-150">For more information, see [Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span></span>  
  
 <span data-ttu-id="ee6b0-151">Ad esempio, il valore xs:double 1.34e1 viene serializzato in 13.4, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ee6b0-151">For example, the xs:double value 1.34e1 is serialized to 13.4 as shown in the following example:</span></span>  
  
```sql
declare @x xml  
set @x =''  
select CAST(@x.query('1.34e1') as nvarchar(50))  
```  
  
 <span data-ttu-id="ee6b0-152">Viene restituito il valore stringa 13.4.</span><span class="sxs-lookup"><span data-stu-id="ee6b0-152">This returns the string value 13.4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6b0-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee6b0-153">See Also</span></span>  
 <span data-ttu-id="ee6b0-154">[Regole del cast dei tipi in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span><span class="sxs-lookup"><span data-stu-id="ee6b0-154">[Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span></span>  
 [<span data-ttu-id="ee6b0-155">CAST e CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ee6b0-155">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
