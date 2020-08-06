---
title: Formattazione XML sul lato client e sul lato server (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- FOR XML clause, formatting
- client-side XML formatting
- server-side XPath
- server-side XML formatting
- AUTO mode
- client-side XPath
ms.assetid: f807ab7a-c5f8-4e61-9b00-23aebfabc47e
author: rothja
ms.author: jroth
ms.openlocfilehash: fa155fc6d346cb90de54e5599aca1c296623faa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630417"
---
# <a name="client-side-vs-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="e77ff-102">Lato client e Formattazione XML sul lato server (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e77ff-102">Client-side vs. Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="e77ff-103">In questo argomento vengono descritte le differenze generali tra la formattazione XML sul lato client e quella sul lato server in SQLXML.</span><span class="sxs-lookup"><span data-stu-id="e77ff-103">This topic describes the general differences between client-side and server-side XML formatting in SQLXML.</span></span>  
  
## <a name="multiple-rowset-queries-not-supported-in-client-side-formatting"></a><span data-ttu-id="e77ff-104">Query su più set di righe non supportate nella formattazione sul lato client</span><span class="sxs-lookup"><span data-stu-id="e77ff-104">Multiple Rowset Queries Not Supported in Client-side Formatting</span></span>  
 <span data-ttu-id="e77ff-105">Le query che generano più set di righe non sono supportate quando si utilizza la formattazione XML sul lato client.</span><span class="sxs-lookup"><span data-stu-id="e77ff-105">Queries that generate multiple rowsets are not supported when you use client-side XML formatting.</span></span> <span data-ttu-id="e77ff-106">Supporre, ad esempio, di disporre di una directory virtuale nella quale è stata specificata la formattazione sul lato client.</span><span class="sxs-lookup"><span data-stu-id="e77ff-106">For example, assume you have a virtual directory in which you have client-side formatting specified.</span></span> <span data-ttu-id="e77ff-107">Si consideri questo modello di esempio, in cui sono presenti due istruzioni SELECT in un **\<sql:query>** blocco:</span><span class="sxs-lookup"><span data-stu-id="e77ff-107">Consider this sample template, which has two SELECT statements in a **\<sql:query>** block:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
     SELECT FirstName FROM Person.Contact FOR XML Nested;   
     SELECT LastName FROM Person.Contact FOR XML Nested    
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-108">È possibile eseguire questo modello nel codice dell'applicazione ma viene restituito un errore, poiché la formattazione XML sul lato client non supporta la formattazione di più set di righe.</span><span class="sxs-lookup"><span data-stu-id="e77ff-108">You can execute this template in application code and an error is returned, because client-side XML formatting does not support formatting of multiple rowsets.</span></span> <span data-ttu-id="e77ff-109">Se si specificano le query in due **\<sql:query>** blocchi distinti, si otterranno i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="e77ff-109">If you specify the queries in two separate **\<sql:query>** blocks, you will get the desired results.</span></span>  
  
## <a name="timestamp-maps-differently-in-client--vs-server-side-formatting"></a><span data-ttu-id="e77ff-110">timestamp viene mappato in modo diverso nella formattazione sul lato client e in quella sul lato server</span><span class="sxs-lookup"><span data-stu-id="e77ff-110">timestamp Maps Differently in Client- vs. Server-side Formatting</span></span>  
 <span data-ttu-id="e77ff-111">Nella formattazione XML sul lato server la colonna di database del tipo `timestamp` esegue il mapping al tipo XDR i8, quando viene specificata l'opzione XMLDATA nella query.</span><span class="sxs-lookup"><span data-stu-id="e77ff-111">In server-side XML formatting, the database column of `timestamp` type maps to the i8 XDR type (when the XMLDATA option is specified in the query).</span></span>  
  
 <span data-ttu-id="e77ff-112">Nella formattazione XML sul lato client la colonna di database del tipo `timestamp` esegue il mapping al tipo XDR `uri` o `bin.base64`, a seconda che venga specificata l'opzione binary base64 nella query.</span><span class="sxs-lookup"><span data-stu-id="e77ff-112">In client-side XML formatting, the database column of `timestamp` type maps to either the `uri` or the `bin.base64` XDR type (depending on whether the binary base64 option is specified in the query).</span></span> <span data-ttu-id="e77ff-113">Il `bin.base64` tipo XDR è utile se si utilizzano le funzionalità updategram e Bulkload, in quanto questo tipo viene convertito nel [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` tipo.</span><span class="sxs-lookup"><span data-stu-id="e77ff-113">The `bin.base64` XDR type is useful if you use the updategram and bulkload features, because this type is converted to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` type.</span></span> <span data-ttu-id="e77ff-114">In questo modo, l'operazione di inserimento, aggiornamento o eliminazione viene eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="e77ff-114">This way, the insert, update, or delete operation succeeds.</span></span>  
  
## <a name="deep-variants-are-used-in-server-side-formatting"></a><span data-ttu-id="e77ff-115">Tipi VARIANT completi utilizzati nella formattazione sul lato server</span><span class="sxs-lookup"><span data-stu-id="e77ff-115">Deep VARIANTs Are Used in Server-side Formatting</span></span>  
 <span data-ttu-id="e77ff-116">Nella formattazione XML sul lato server vengono utilizzati i tipi VARIANT completi.</span><span class="sxs-lookup"><span data-stu-id="e77ff-116">In server-side XML formatting, the deep types of a VARIANT type are used.</span></span> <span data-ttu-id="e77ff-117">Se si utilizza la formattazione XML sul lato client, le varianti vengono convertite in una stringa Unicode e i sottotipi di VARIANT non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="e77ff-117">If you use client-side XML formatting, the variants are converted to Unicode string, and the subtypes of VARIANT are not used.</span></span>  
  
## <a name="nested-mode-vs-auto-mode"></a><span data-ttu-id="e77ff-118">Modalità NESTED e modalità AUTO</span><span class="sxs-lookup"><span data-stu-id="e77ff-118">NESTED Mode vs. AUTO Mode</span></span>  
 <span data-ttu-id="e77ff-119">La modalità NESTED di FOR XML sul lato client è simile alla modalità AUTO di FOR XML sul lato server, con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e77ff-119">The NESTED mode of the client-side FOR XML is similar to the AUTO mode of server-side FOR XML, with the following exceptions:</span></span>  
  
### <a name="when-you-query-views-using-auto-mode-on-the-server-side-the-view-name-is-returned-as-the-element-name-in-the-resulting-xml"></a><span data-ttu-id="e77ff-120">Quando si esegue una query sulle viste utilizzando la modalità AUTO sul lato server, viene restituito il nome della vista come nome dell'elemento nel codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="e77ff-120">When you query views using AUTO mode on the server-side, the view name is returned as the element name in the resulting XML.</span></span>  
 <span data-ttu-id="e77ff-121">Si supponga, ad esempio, che venga creata la vista seguente nella tabella Person. Contact in AdventureWorksdatabase:</span><span class="sxs-lookup"><span data-stu-id="e77ff-121">For example, assume that the following view is created on the Person.Contact table in the AdventureWorksdatabase:</span></span>  
  
```  
CREATE VIEW ContactView AS (SELECT ContactID as CID,  
                               FirstName  as FName,  
                               LastName  as LName  
                        FROM Person.Contact)  
```  
  
 <span data-ttu-id="e77ff-122">Nel modello seguente viene specificata una query sulla vista ContactView e viene inoltre specificata la formattazione XML sul lato server:</span><span class="sxs-lookup"><span data-stu-id="e77ff-122">The following template specifies a query against the ContactView view, and also specifies server-side XML formatting:</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT *  
    FROM   ContactView  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-123">Quando si esegue il modello, viene restituito il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="e77ff-123">When you execute the template, the following XML is returned.</span></span> <span data-ttu-id="e77ff-124">Vengono visualizzati solo i risultati parziali. Si noti che i nomi degli elementi sono i nomi delle visualizzazioni in cui viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="e77ff-124">(Only partial results are shown.) Note that the element names are the names of the views against which the query is executed.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ContactView CID="1" FName="Gustavo" LName="Achong" />   
  <ContactView CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-125">Quando si specifica la formattazione XML sul lato client tramite la modalità NESTED corrispondente, vengono restituiti i nomi delle tabelle di base come nomi degli elementi nel codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="e77ff-125">When you specify client-side XML formatting by using the corresponding NESTED mode, the base table name(s) are returned as the element name(s) in the resulting XML.</span></span> <span data-ttu-id="e77ff-126">Il modello modificato seguente, ad esempio, esegue la stessa istruzione SELECT, ma la formattazione XML viene eseguita sul lato client (ovvero, **client-side-xml** è impostato su true nel modello):</span><span class="sxs-lookup"><span data-stu-id="e77ff-126">For example, the following revised template executes the same SELECT statement, but the XML formatting is performed on the client-side (that is, **client-side-xml** is set to true in the template):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT *  
    FROM   ContactView  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-127">L'esecuzione di questo modello genera il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="e77ff-127">Executing this template produces the following XML.</span></span> <span data-ttu-id="e77ff-128">Notare che in questo caso il nome dell'elemento è il nome della tabella di base.</span><span class="sxs-lookup"><span data-stu-id="e77ff-128">Note that the element name is the base table name in this case.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact CID="1" FName="Gustavo" LName="Achong" />   
  <Person.Contact CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
### <a name="when-you-use-auto-mode-of-the-server-side-for-xml-the-table-aliases-specified-in-the-query-are-returned-as-element-names-in-the-resulting-xml"></a><span data-ttu-id="e77ff-129">Quando si utilizza la modalità AUTO di FOR XML sul lato server, vengono restituiti gli alias delle tabelle specificati nella query come nomi degli elementi nel codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="e77ff-129">When you use AUTO mode of the server-side FOR XML, the table aliases specified in the query are returned as element names in the resulting XML.</span></span>  
 <span data-ttu-id="e77ff-130">Considerare ad esempio il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="e77ff-130">For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-131">L'esecuzione di questo modello genera il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="e77ff-131">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <C fname="Gustavo" lname="Achong" />   
  <C fname="Catherine" lname="Abel" />   
...  
</ROOT>   
```  
  
 <span data-ttu-id="e77ff-132">Quando si utilizza la modalità NESTED di FOR XML sul lato client, vengono restituiti i nomi delle tabelle come nomi degli elementi nel codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="e77ff-132">When you use the NESTED mode of the client-side FOR XML, the table names are returned as element names in the resulting XML.</span></span> <span data-ttu-id="e77ff-133">Gli alias di tabella specificati nella query non vengono utilizzati. Si consideri, ad esempio, il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="e77ff-133">(Table aliases that are specified in the query are not used.) For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-134">L'esecuzione di questo modello genera il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="e77ff-134">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact fname="Gustavo" lname="Achong" />   
  <Person.Contact fname="Catherine" lname="Abel" />   
...  
</ROOT>  
```  
  
### <a name="if-you-have-a-query-that-returns-columns-as-dbobject-queries-you-cannot-use-aliases-for-these-columns"></a><span data-ttu-id="e77ff-135">Se si dispone di una query che restituisce colonne come query dbobject, non è possibile utilizzare gli alias per tali colonne.</span><span class="sxs-lookup"><span data-stu-id="e77ff-135">If you have a query that returns columns as dbobject queries, you cannot use aliases for these columns.</span></span>  
 <span data-ttu-id="e77ff-136">Considerare ad esempio il modello seguente in cui viene eseguita una query che restituisce un ID dipendente e una foto.</span><span class="sxs-lookup"><span data-stu-id="e77ff-136">For example, consider the following template, which executes a query that returns an employee ID and a photo.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query client-side-xml="1">  
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML NESTED, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-137">L'esecuzione di questo modello restituisce la colonna Photo come query dbobject.</span><span class="sxs-lookup"><span data-stu-id="e77ff-137">Executing this template returns the Photo column as a dbobject query.</span></span> <span data-ttu-id="e77ff-138">In questa query dbobject `@P` si riferisce a un nome della colonna che non esiste.</span><span class="sxs-lookup"><span data-stu-id="e77ff-138">In this dbobject query, `@P` refers to a column name that does not exist.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@P</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-139">Se la formattazione XML viene eseguita sul server (**client-side-xml = "0"**), è possibile usare l'alias per le colonne che restituiscono query dbobject in cui vengono restituiti i nomi effettivi delle tabelle e delle colonne (anche se sono stati specificati alias).</span><span class="sxs-lookup"><span data-stu-id="e77ff-139">If the XML formatting is done on the server (**client-side-xml="0"**), you can use the alias for the columns that return dbobject queries in which actual table and column names are returned (even if you have aliases specified).</span></span> <span data-ttu-id="e77ff-140">Il modello seguente, ad esempio, esegue una query e la formattazione XML viene eseguita sul server (l'opzione **client-side-xml** non è specificata e l'opzione **Esegui su client** non è selezionata per la radice virtuale).</span><span class="sxs-lookup"><span data-stu-id="e77ff-140">For example, the following template executes a query, and the XML formatting is done on the server (the **client-side-xml** option is not specified and the **Run On Client** option is not selected for the virtual root).</span></span> <span data-ttu-id="e77ff-141">La query specifica anche la modalità AUTO (non la modalità NESTED sul lato client).</span><span class="sxs-lookup"><span data-stu-id="e77ff-141">The query also specifies AUTO mode (not the client-side NESTED mode).</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query   
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML AUTO, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e77ff-142">Quando viene eseguito questo modello, viene restituito il documento XML seguente (notare che non vengono utilizzati gli alias nella query dbobject per la colonna LargePhoto):</span><span class="sxs-lookup"><span data-stu-id="e77ff-142">When this template is executed, the following XML document is returned (note that aliases are not used in the dbobject query for the LargePhoto column):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@LargePhoto</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
### <a name="client-side-vs-server-side-xpath"></a><span data-ttu-id="e77ff-143">XPath sul lato client e sul lato server</span><span class="sxs-lookup"><span data-stu-id="e77ff-143">Client-side vs. Server-side XPath</span></span>  
 <span data-ttu-id="e77ff-144">XPath sul lato client e XPath sul lato server funzionano allo stesso modo ad eccezione delle seguenti differenze:</span><span class="sxs-lookup"><span data-stu-id="e77ff-144">Client-side XPath and server-side XPath work the same except for these differences:</span></span>  
  
-   <span data-ttu-id="e77ff-145">Le conversioni dei dati applicate quando si utilizzano le query XPath sul lato client sono diverse da quelle applicate quando si utilizzano le query XPath sul lato server.</span><span class="sxs-lookup"><span data-stu-id="e77ff-145">The data conversions that are applied when you use client-side XPath queries are different from those that are applied when you use server-side XPath queries.</span></span> <span data-ttu-id="e77ff-146">XPath sul lato client utilizza la modalità CAST anziché la modalità CONVERT 126.</span><span class="sxs-lookup"><span data-stu-id="e77ff-146">Client-side XPath uses CAST instead of CONVERT mode 126.</span></span>  
  
-   <span data-ttu-id="e77ff-147">Quando si specifica **client-side-xml = "0"** (false) in un modello, viene richiesta la formattazione XML sul lato server.</span><span class="sxs-lookup"><span data-stu-id="e77ff-147">When you specify **client-side-xml="0"** (false) in a template, you are requesting server-side XML formatting.</span></span> <span data-ttu-id="e77ff-148">Pertanto, non è possibile specificare FOR XML NESTED poiché il server non riconosce l'opzione NESTED</span><span class="sxs-lookup"><span data-stu-id="e77ff-148">Therefore, you cannot specify FOR XML NESTED because the server does not recognize the NESTED option.</span></span> <span data-ttu-id="e77ff-149">e viene quindi generato un errore.</span><span class="sxs-lookup"><span data-stu-id="e77ff-149">This generates an error.</span></span> <span data-ttu-id="e77ff-150">È necessario utilizzare le modalità AUTO, RAW o EXPLICIT riconosciute dal server.</span><span class="sxs-lookup"><span data-stu-id="e77ff-150">You must use the AUTO, RAW, or EXPLICIT modes, which the server does recognize.</span></span>  
  
-   <span data-ttu-id="e77ff-151">Quando si specifica **client-side-xml = "1"** (true) in un modello, viene richiesta la formattazione XML sul lato client.</span><span class="sxs-lookup"><span data-stu-id="e77ff-151">When you specify **client-side-xml="1"** (true) in a template, you are requesting client-side XML formatting.</span></span> <span data-ttu-id="e77ff-152">In questo caso, è possibile specificare FOR XML NESTED.</span><span class="sxs-lookup"><span data-stu-id="e77ff-152">In this case, you can specify FOR XML NESTED.</span></span> <span data-ttu-id="e77ff-153">Se si specifica FOR XML AUTO, la formattazione XML viene eseguita sul lato server anche se nel modello è specificato **client-side-xml = "1"** .</span><span class="sxs-lookup"><span data-stu-id="e77ff-153">If you specify FOR XML AUTO, the XML formatting occurs on the server side although **client-side-xml="1"** is specified in the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77ff-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e77ff-154">See Also</span></span>  
 <span data-ttu-id="e77ff-155">[Considerazioni sulla sicurezza per XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="e77ff-155">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="e77ff-156">[Formattazione XML sul lato client &#40;SQLXML 4,0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="e77ff-156">[Client-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="e77ff-157">Formattazione XML sul lato server &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e77ff-157">Server-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](server-side-xml-formatting-sqlxml-4-0.md)  
  
  
