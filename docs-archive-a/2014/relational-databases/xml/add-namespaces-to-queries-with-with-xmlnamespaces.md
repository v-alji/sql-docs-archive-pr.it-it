---
title: Aggiungere spazi dei nomi alle query con WITH XMLNAMESPACES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENTS XSINIL directive
- adding namespaces
- XSINIL directive
- default namespaces
- queries [XML in SQL Server], WITH XMLNAMESPACES clause
- predefined namespaces [XML in SQL Server]
- FOR XML clause, WITH XMLNAMESPACES clause
- namespaces [XML in SQL Server]
- xml data type [SQL Server], WITH XMLNAMESPACES clause
- WITH XMLNAMESPACES clause
ms.assetid: 2189cb5e-4460-46c5-a254-20c833ebbfec
author: rothja
ms.author: jroth
ms.openlocfilehash: ed5d719a845996215fffc18af64401779f848cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623955"
---
# <a name="add-namespaces-to-queries-with-with-xmlnamespaces"></a><span data-ttu-id="dcadb-102">Aggiungere spazi dei nomi alle query con WITH XMLNAMESPACES</span><span class="sxs-lookup"><span data-stu-id="dcadb-102">Add Namespaces to Queries with WITH XMLNAMESPACES</span></span>
  <span data-ttu-id="dcadb-103">La clausola[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) offre il supporto dell'URI dello spazio dei nomi nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="dcadb-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) provides namespace URI support in the following way:</span></span>  
  
-   <span data-ttu-id="dcadb-104">Rende disponibile il mapping tra il prefisso dello spazio dei nomi e l'URI durante le query di [costruzione di codice XML tramite la clausola FOR XML](for-xml-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="dcadb-104">It makes the namespace prefix to URI mapping available when [Constructing XML Using FOR XML](for-xml-sql-server.md) queries.</span></span>  
  
-   <span data-ttu-id="dcadb-105">Rende disponibile il mapping tra lo spazio dei nomi e l'URI nel contesto dello spazio dei nomi statico dei [metodi con tipo di dati XML](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="dcadb-105">It makes the namespace to URI mapping available to the static namespace context of the [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span>  
  
## <a name="using-with-xmlnamespaces-in-the-for-xml-queries"></a><span data-ttu-id="dcadb-106">Utilizzo di WITH XMLNAMESPACES nelle query FOR XML</span><span class="sxs-lookup"><span data-stu-id="dcadb-106">Using WITH XMLNAMESPACES in the FOR XML Queries</span></span>  
 <span data-ttu-id="dcadb-107">WITH XMLNAMESPACES consente di includere gli spazi dei nomi XML nelle query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="dcadb-107">WITH XMLNAMESPACES lets you include XML namespaces in FOR XML queries.</span></span> <span data-ttu-id="dcadb-108">Si consideri, ad esempio, la query FOR XML seguente:</span><span class="sxs-lookup"><span data-stu-id="dcadb-108">For example, consider the following FOR XML query:</span></span>  
  
```  
SELECT ProductID, Name, Color  
FROM   Production.Product  
WHERE  ProductID=316 or ProductID=317  
FOR XML RAW  
```  
  
 <span data-ttu-id="dcadb-109">Risultato:</span><span class="sxs-lookup"><span data-stu-id="dcadb-109">This is the result:</span></span>  
  
```  
<row ProductID="316" Name="Blade" />  
<row ProductID="317" Name="LL Crankarm" Color="Black" />  
  
```  
  
 <span data-ttu-id="dcadb-110">Per aggiungere spazi dei nomi al codice XML creato dalla query FOR XML, specificare innanzitutto il mapping tra il prefisso dello spazio dei nomi e l'URI utilizzando la clausola WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="dcadb-110">To add namespaces to the XML constructed by the FOR XML query, first specify the namespace prefix to URI mappings by using the WITH NAMESPACES clause.</span></span> <span data-ttu-id="dcadb-111">Utilizzare quindi i prefissi dello spazio dei nomi per specificare i nomi nella query, come illustrato nella query modificata seguente.</span><span class="sxs-lookup"><span data-stu-id="dcadb-111">Then, use the namespace prefixes in specifying the names in the query as shown in the following modified query.</span></span> <span data-ttu-id="dcadb-112">Si noti che la clausola WITH XMLNAMESPACES specifica il mapping tra il prefisso dello spazio dei nomi (`ns1`) e l'URI (`uri`).</span><span class="sxs-lookup"><span data-stu-id="dcadb-112">Note that the WITH XMLNAMESPACES clause specifies the namespace prefix (`ns1`) to URI (`uri`) mapping.</span></span> <span data-ttu-id="dcadb-113">Il prefisso `ns1` viene quindi utilizzato per specificare i nomi degli elementi e degli attributi che devono essere creati per la query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="dcadb-113">The `ns1` prefix is then used in specifying the element and attribute names to be constructed by the FOR XML query.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Prod'), ELEMENTS  
  
```  
  
 <span data-ttu-id="dcadb-114">Il risultato XML include i prefissi dello spazio dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dcadb-114">The XML result includes the namespace prefixes:</span></span>  
  
```  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
</ns1:Prod>  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>317</ns1:ProductID>  
  <ns1:Name>LL Crankarm</ns1:Name>  
  <ns1:Color>Black</ns1:Color>  
</ns1:Prod>  
  
```  
  
 <span data-ttu-id="dcadb-115">Per la clausola WITH XMLNAMESPACES sono valide le osservazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dcadb-115">The following applies to the WITH XMLNAMESPACES clause:</span></span>  
  
-   <span data-ttu-id="dcadb-116">La clausola è supportata solo nelle modalità RAW, AUTO e PATH delle query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="dcadb-116">It is supported only on the RAW, AUTO, and PATH modes of the FOR XML queries.</span></span> <span data-ttu-id="dcadb-117">La modalità EXPLICIT non è supportata.</span><span class="sxs-lookup"><span data-stu-id="dcadb-117">The EXPLICIT mode is not supported.</span></span>  
  
-   <span data-ttu-id="dcadb-118">La clausola influisce solo sui prefissi dello spazio dei nomi delle query FOR XML e sui metodi con tipo di dati **xml** , ma non sul parser XML.</span><span class="sxs-lookup"><span data-stu-id="dcadb-118">It only affects the namespace prefixes of FOR XML queries and the **xml** data type methods, but not the XML parser.</span></span> <span data-ttu-id="dcadb-119">Ad esempio, la query seguente restituisce un errore perché nel documento XML non è disponibile una dichiarazione dello spazio dei nomi per il prefisso myNS.</span><span class="sxs-lookup"><span data-stu-id="dcadb-119">For example, the following query returns an error, because the XML document has no namespace declaration for the myNS prefix.</span></span>  
  
-   <span data-ttu-id="dcadb-120">Se si utilizza una clausola WITH XMLNAMESPACES, non è possibile utilizzare le direttive FOR XML, ovvero XMLSCHEMA e XMLDATA.</span><span class="sxs-lookup"><span data-stu-id="dcadb-120">The FOR XML directives, XMLSCHEMA and XMLDATA cannot be used when a WITH XMLNAMESPACES clause is being used.</span></span>  
  
    ```  
    CREATE TABLE T (x xml)  
    go  
    WITH XMLNAMESPACES ('http://abc' as myNS )  
    INSERT INTO T VALUES('<myNS:root/>')  
    ```  
  
## <a name="using-the-xsinil-directive"></a><span data-ttu-id="dcadb-121">Utilizzo della direttiva XSINIL</span><span class="sxs-lookup"><span data-stu-id="dcadb-121">Using the XSINIL Directive</span></span>  
 <span data-ttu-id="dcadb-122">Se si utilizza la direttiva ELEMENTS XSINIL, non è possibile definire il prefisso xsi nella clausola WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="dcadb-122">You cannot define the xsi prefix in the WITH XMLNAMESPACES clause if you are using the ELEMENTS XSINIL directive.</span></span> <span data-ttu-id="dcadb-123">Questo prefisso viene infatti aggiunto automaticamente quando si utilizza ELEMENTS XSINIL.</span><span class="sxs-lookup"><span data-stu-id="dcadb-123">Instead, it is added automatically when you use ELEMENTS XSINIL.</span></span> <span data-ttu-id="dcadb-124">La query seguente usa ELEMENTS XSINIL che genera codice XML incentrato sugli elementi nel quale viene eseguito il mapping dei valori Null a elementi con l'attributo **xsi:nil** impostato su True.</span><span class="sxs-lookup"><span data-stu-id="dcadb-124">The following query uses ELEMENTS XSINIL that generates element-centric XML where null values are mapped to elements that have the **xsi:nil** attribute set to True.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316   
FOR XML RAW, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="dcadb-125">Risultato:</span><span class="sxs-lookup"><span data-stu-id="dcadb-125">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
  <ns1:Color xsi:nil="true" />  
</row>  
```  
  
## <a name="specifying-default-namespaces"></a><span data-ttu-id="dcadb-126">Impostazione degli spazi dei nomi predefiniti</span><span class="sxs-lookup"><span data-stu-id="dcadb-126">Specifying Default Namespaces</span></span>  
 <span data-ttu-id="dcadb-127">Anziché dichiarare un prefisso dello spazio dei nomi, è possibile dichiarare uno spazio dei nomi predefinito utilizzando la parola chiave DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="dcadb-127">Instead of declaring a namespace prefix, you can declare a default namespace by using a DEFAULT keyword.</span></span> <span data-ttu-id="dcadb-128">Nella query FOR XML, questa parola chiave associa lo spazio dei nomi predefinito ai nodi XML nel codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="dcadb-128">In the FOR XML query, it will bind the default namespace to XML nodes in the resulting XML.</span></span> <span data-ttu-id="dcadb-129">Nell'esempio seguente, la clausola WITH XMLNAMESPACES definisce due prefissi di spazio dei nomi che vengono definiti insieme a uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="dcadb-129">In the following example, the WITH XMLNAMESPACES defines two namespace prefixes that are defined together with a default namespace.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,   
                    'uri2' as ns2,  
                    DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product   
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Product'), ROOT('ns2:root'), ELEMENTS  
```  
  
 <span data-ttu-id="dcadb-130">La query FOR XML genera codice XML incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="dcadb-130">The FOR XML query generates element-centric XML.</span></span> <span data-ttu-id="dcadb-131">Si noti che nella query entrambi i prefissi dello spazio dei nomi vengono utilizzati per la denominazione dei nodi.</span><span class="sxs-lookup"><span data-stu-id="dcadb-131">Note that the query uses both the namespace prefixes in naming nodes.</span></span> <span data-ttu-id="dcadb-132">Nella clausola SELECT, per l'ID prodotto, il nome e il colore non è specificato un nome con un prefisso</span><span class="sxs-lookup"><span data-stu-id="dcadb-132">In the SELECT clause, the ProductID, Name, and Color do not specify a name with any prefix.</span></span> <span data-ttu-id="dcadb-133">e pertanto gli elementi corrispondenti nel codice XML risultante appartengono allo spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="dcadb-133">Therefore, the corresponding elements in the resulting XML belong to the default namespace.</span></span>  
  
```  
<ns2:root xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">  
  <ns1:Product>  
    <ProductID>316</ProductID>  
    <Name>Blade</Name>  
  </ns1:Product>  
  <ns1:Product>  
    <ProductID>317</ProductID>  
    <Name>LL Crankarm</Name>  
    <Color>Black</Color>  
  </ns1:Product>  
</ns2:root>  
```  
  
 <span data-ttu-id="dcadb-134">La query seguente è simile alla precedente, eccetto che per il fatto che è specificata la modalità FOR XML AUTO.</span><span class="sxs-lookup"><span data-stu-id="dcadb-134">The following query is similar to the previous one, except that the FOR XML AUTO mode is specified.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,  'uri2' as ns2,DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product as "ns1:Product"  
WHERE ProductID=316 or ProductID=317  
FOR XML AUTO, ROOT('ns2:root'), ELEMENTS  
```  
  
## <a name="using-predefined-namespaces"></a><span data-ttu-id="dcadb-135">Utilizzo degli spazi dei nomi predefiniti</span><span class="sxs-lookup"><span data-stu-id="dcadb-135">Using Predefined Namespaces</span></span>  
 <span data-ttu-id="dcadb-136">Quando si utilizzano gli spazi dei nomi predefiniti, è necessario specificare in modo esplicito l'associazione degli spazi dei nomi utilizzando WITH XMLNAMESPACES. Questa osservazione non è valida per lo spazio dei nomi xml e per lo spazio dei nomi xsi se si utilizza ELEMENTS XSINIL</span><span class="sxs-lookup"><span data-stu-id="dcadb-136">When you use predefined namespaces, except the xml namespace and the xsi namespace when ELEMENTS XSINIL is used, you must explicitly specify the namespace binding by using WITH XMLNAMESPACES.</span></span> <span data-ttu-id="dcadb-137">La query seguente definisce in modo esplicito l'associazione tra il prefisso dello spazio dei nomi e l'URI per lo spazio dei nomi predefinito (`urn:schemas-microsoft-com:xml-sql`).</span><span class="sxs-lookup"><span data-stu-id="dcadb-137">The following query explicitly defines the namespace prefix to URI binding for the predefined namespace (`urn:schemas-microsoft-com:xml-sql`).</span></span>  
  
```  
WITH XMLNAMESPACES ('urn:schemas-microsoft-com:xml-sql' as sql)  
SELECT 'SELECT * FROM Customers FOR XML AUTO, ROOT("a")' AS "sql:query"  
FOR XML PATH('sql:root')  
```  
  
 <span data-ttu-id="dcadb-138">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="dcadb-138">This is the result.</span></span> <span data-ttu-id="dcadb-139">Gli utenti di SQLXML hanno familiarità con questo modello XML.</span><span class="sxs-lookup"><span data-stu-id="dcadb-139">SQLXML users are familiar with this XML template.</span></span> <span data-ttu-id="dcadb-140">Per altre informazioni, vedere [Concetti relativi alla programmazione SQLXML 4.0](../sqlxml/sqlxml-4-0-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="dcadb-140">For more information, see [SQLXML 4.0 Programming Concepts](../sqlxml/sqlxml-4-0-programming-concepts.md).</span></span>  
  
```  
<sql:root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>SELECT * FROM Customers FOR XML AUTO, ROOT("a")</sql:query>  
</sql:root>  
```  
  
 <span data-ttu-id="dcadb-141">Il prefisso dello spazio dei nomi xml è l'unico che può essere utilizzato senza che sia necessario definirlo in modo esplicito in WITH XMLNAMESPACES, come illustrato nella query seguente in modalità PATH.</span><span class="sxs-lookup"><span data-stu-id="dcadb-141">Only the xml namespace prefix can be used without explicitly defining it in WITH XMLNAMESPACES, as shown in the following PATH mode query.</span></span> <span data-ttu-id="dcadb-142">Se si dichiara questo prefisso, è anche necessario associarlo allo spazio dei nomi http://www.w3.org/XML/1998/namespace.</span><span class="sxs-lookup"><span data-stu-id="dcadb-142">Also, if the prefix is declared, it has to be bound to the namespace http://www.w3.org/XML/1998/namespace.</span></span> <span data-ttu-id="dcadb-143">I nomi specificati nella clausola SELECT fanno riferimento al prefisso dello spazio dei nomi xml che non viene definito in modo esplicito tramite WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="dcadb-143">The names specified in the SELECT clause refer to the xml namespace prefix that is not explicitly defined by using WITH XMLNAMESPACES.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
go  
```  
  
 <span data-ttu-id="dcadb-144">Gli attributi @xml:lang usano lo spazio dei nomi xml predefinito.</span><span class="sxs-lookup"><span data-stu-id="dcadb-144">The @xml:lang attributes use the predefined xml namespace.</span></span> <span data-ttu-id="dcadb-145">Poiché nella versione XML 1.0 non è necessario dichiarare in modo esplicito l'associazione dello spazio dei nomi xml, il risultato non includerà una dichiarazione esplicita di tale associazione.</span><span class="sxs-lookup"><span data-stu-id="dcadb-145">Because XML version 1.0 does not require the explicit declaration of the xml namespace binding, the result will not include an explicit declaration of the namespace binding.</span></span>  
  
 <span data-ttu-id="dcadb-146">Risultato:</span><span class="sxs-lookup"><span data-stu-id="dcadb-146">This is the result:</span></span>  
  
```  
<Translation>  
  <English xml:lang="en">food</English>  
  <German xml:lang="ger">Essen</German>  
</Translation>  
```  
  
## <a name="using-with-xmlnamespaces-with-the-xml-data-type-methods"></a><span data-ttu-id="dcadb-147">Utilizzo di WITH XMLNAMESPACES con i metodi con tipo di dati xml</span><span class="sxs-lookup"><span data-stu-id="dcadb-147">Using WITH XMLNAMESPACES with the xml Data Type Methods</span></span>  
 <span data-ttu-id="dcadb-148">Tutti i [metodi con tipo di dati xml](/sql/t-sql/xml/xml-data-type-methods) specificati in una query SELECT o in UPDATE quando si tratta del metodo **modify()** , devono ripetere la dichiarazione dello spazio dei nomi nel prologo.</span><span class="sxs-lookup"><span data-stu-id="dcadb-148">The [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) specified in a SELECT query, or in UPDATE when it is the **modify()** method, all have to repeat the namespace declaration in their prolog.</span></span> <span data-ttu-id="dcadb-149">e possono richiedere pertanto molto tempo.</span><span class="sxs-lookup"><span data-stu-id="dcadb-149">This can be time-consuming.</span></span> <span data-ttu-id="dcadb-150">Ad esempio, la query seguente recupera gli ID dei modelli di prodotto per i quali esistono specifiche nelle descrizioni del catalogo,</span><span class="sxs-lookup"><span data-stu-id="dcadb-150">For example, the following query retrieves product model IDs whose catalog descriptions do include specification.</span></span> <span data-ttu-id="dcadb-151">ovvero per i quali esiste l'elemento <`Specifications`>.</span><span class="sxs-lookup"><span data-stu-id="dcadb-151">That is, the <`Specifications`> element exists.</span></span>  
  
```  
SELECT ProductModelID, CatalogDescription.query('  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
    declare namespace  pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
```  
  
 <span data-ttu-id="dcadb-152">Nella query precedente, entrambi i metodi **query()** e **exist()** dichiarano lo stesso spazio dei nomi nel rispettivo prologo.</span><span class="sxs-lookup"><span data-stu-id="dcadb-152">In the previous query, both the **query()** and **exist()** methods declare the same namespace in their prolog.</span></span> <span data-ttu-id="dcadb-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dcadb-153">For example:</span></span>  
  
```  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
```  
  
 <span data-ttu-id="dcadb-154">In alternativa, è possibile dichiarare innanzitutto WITH XMLNAMESPACES e utilizzare i prefissi dello spazio dei nomi nella query.</span><span class="sxs-lookup"><span data-stu-id="dcadb-154">Alternatively, you can declare WITH XMLNAMESPACES first and use the namespace prefixes in the query.</span></span> <span data-ttu-id="dcadb-155">In questo caso, non è necessario che i metodi **query()** e **exist()** includano le dichiarazioni di spazio dei nomi nel prologo.</span><span class="sxs-lookup"><span data-stu-id="dcadb-155">In this case, the **query()** and **exist()** methods  do not have to include namespace declarations in their prolog.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' as pd)  
SELECT ProductModelID, CatalogDescription.query('  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
Go  
```  
  
 <span data-ttu-id="dcadb-156">Si noti che una dichiarazione esplicita nel prologo della query XQuery ignora il prefisso e lo spazio dei nomi predefinito definiti nella clausola WITH.</span><span class="sxs-lookup"><span data-stu-id="dcadb-156">Note that an explicit declaration in the XQuery prolog overrides the namespace prefix and the default element namespace that are defined in the WITH clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcadb-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcadb-157">See Also</span></span>  
 <span data-ttu-id="dcadb-158">[metodi con tipo di dati XML](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="dcadb-158">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="dcadb-159">[Riferimento al linguaggio XQuery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span><span class="sxs-lookup"><span data-stu-id="dcadb-159">[XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span></span>  
 <span data-ttu-id="dcadb-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span><span class="sxs-lookup"><span data-stu-id="dcadb-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span></span>  
 [<span data-ttu-id="dcadb-161">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcadb-161">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
