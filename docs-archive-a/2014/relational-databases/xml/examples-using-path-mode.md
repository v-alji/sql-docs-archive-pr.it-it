---
title: 'Esempi: Utilizzo della modalità PATH | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, examples
ms.assetid: 3564e13b-9b97-49ef-8cf9-6a78677b09a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0876d93ffe246b6129a3838f8dbae47f3be7ffaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726783"
---
# <a name="examples-using-path-mode"></a><span data-ttu-id="b35b5-102">Esempi: Uso della modalità PATH</span><span class="sxs-lookup"><span data-stu-id="b35b5-102">Examples: Using PATH Mode</span></span>
  <span data-ttu-id="b35b5-103">Negli esempi seguenti viene illustrato l'utilizzo della modalità PATH nella creazione di codice XML da una query SELECT.</span><span class="sxs-lookup"><span data-stu-id="b35b5-103">The following examples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="b35b5-104">Molte di queste query vengono specificate sui documenti XML di istruzioni per la produzione di biciclette archiviate nella colonna Instructions della tabella ProductModel.</span><span class="sxs-lookup"><span data-stu-id="b35b5-104">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="specifying-a-simple-path-mode-query"></a><span data-ttu-id="b35b5-105">Specifica di una query semplice in modalità PATH</span><span class="sxs-lookup"><span data-stu-id="b35b5-105">Specifying a simple PATH mode query</span></span>  
 <span data-ttu-id="b35b5-106">La query seguente specifica una modalità FOR XML PATH.</span><span class="sxs-lookup"><span data-stu-id="b35b5-106">This query specifies a FOR XML PATH mode.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   
       ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH;  
GO  
```  
  
 <span data-ttu-id="b35b5-107">Il risultato seguente è codice XML incentrato sugli elementi in cui il valore di ogni colonna nel set di righe risultante viene inserito in un elemento.</span><span class="sxs-lookup"><span data-stu-id="b35b5-107">The following result is element-centric XML where each column value in the resulting rowset is wrapped in an element.</span></span> <span data-ttu-id="b35b5-108">Poiché la clausola `SELECT` non specifica alcun alias per i nomi delle colonne, i nomi degli elementi figlio generati sono gli stessi nomi di colonna corrispondenti nella clausola `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="b35b5-108">Because the `SELECT` clause does not specify any aliases for the column names, the child element names generated are the same as the corresponding column names in the `SELECT` clause.</span></span> <span data-ttu-id="b35b5-109">Per ogni riga del set di righe viene aggiunto un tag <`row`>.</span><span class="sxs-lookup"><span data-stu-id="b35b5-109">For each row in the rowset a <`row`> tag is added.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</row>`  
  
 `<row>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</row>`  
  
 <span data-ttu-id="b35b5-110">Il risultato seguente corrisponde a quello della query in modalità `RAW` con l'opzione `ELEMENTS` specificata.</span><span class="sxs-lookup"><span data-stu-id="b35b5-110">The following result is the same as the `RAW` mode query with the `ELEMENTS` option specified.</span></span> <span data-ttu-id="b35b5-111">Restituisce codice XML incentrato sugli elementi con un elemento <`row`> predefinito per ogni riga del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b35b5-111">It returns element-centric XML with a default <`row`> element for each row in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML RAW, ELEMENTS;  
```  
  
 <span data-ttu-id="b35b5-112">È inoltre possibile specificare che il nome dell'elemento riga sovrascriva l'elemento <`row`> predefinito.</span><span class="sxs-lookup"><span data-stu-id="b35b5-112">You can optionally specify the row element name to overwrite the default <`row`>.</span></span> <span data-ttu-id="b35b5-113">Ad esempio, la query seguente restituisce l'elemento <`ProductModel`> per ogni riga del set di righe.</span><span class="sxs-lookup"><span data-stu-id="b35b5-113">For example, the following query returns the <`ProductModel`> element for each row in the rowset.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModel');  
GO  
```  
  
 <span data-ttu-id="b35b5-114">Il codice XML risultante avrà il nome dell'elemento riga specificato.</span><span class="sxs-lookup"><span data-stu-id="b35b5-114">The resulting XML will have a specified row element name.</span></span>  
  
 `<ProductModel>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ProductModel>`  
  
 `<ProductModel>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ProductModel>`  
  
 <span data-ttu-id="b35b5-115">Se viene specificata una stringa di lunghezza zero, l'elemento di wrapping non viene prodotto.</span><span class="sxs-lookup"><span data-stu-id="b35b5-115">If you specify a zero-length string, the wrapping element is not produced.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('');  
GO  
```  
  
 <span data-ttu-id="b35b5-116">Risultato:</span><span class="sxs-lookup"><span data-stu-id="b35b5-116">This is the result:</span></span>  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
## <a name="specifying-xpath-like-column-names"></a><span data-ttu-id="b35b5-117">Specifica di nomi di colonna in formato XPath</span><span class="sxs-lookup"><span data-stu-id="b35b5-117">Specifying XPath-like column names</span></span>  
 <span data-ttu-id="b35b5-118">Nella query seguente il nome di colonna `ProductModelID` specificato inizia con "\@" e non contiene una barra ("/").</span><span class="sxs-lookup"><span data-stu-id="b35b5-118">In the following query the `ProductModelID` column name specified starts with '\@' and does not contain a slash mark ('/').</span></span> <span data-ttu-id="b35b5-119">Nel codice XML risultante viene pertanto creato un attributo dell'elemento <`row`> con il valore di colonna corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b35b5-119">Therefore, an attribute of the <`row`> element that has the corresponding column value is created in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('ProductModelData');  
GO  
```  
  
 <span data-ttu-id="b35b5-120">Risultato:</span><span class="sxs-lookup"><span data-stu-id="b35b5-120">This is the result:</span></span>  
  
 `< ProductModelData id="122">`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ ProductModelData >`  
  
 `< ProductModelData id="119">`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ ProductModelData >`  
  
 <span data-ttu-id="b35b5-121">È possibile aggiungere un singolo elemento di livello principale specificando l'opzione `root` in `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="b35b5-121">You can add a single top-level element by specifying the `root` option in `FOR XML`.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="b35b5-122">Per creare una gerarchia è possibile includere una sintassi di tipo PATH.</span><span class="sxs-lookup"><span data-stu-id="b35b5-122">To generate a hierarchy, you can include PATH-like syntax.</span></span> <span data-ttu-id="b35b5-123">Ad esempio, modificando il nome della colonna da `Name` in "SomeChild/ModelName", si otterrà una struttura XML gerarchica, come illustrato nel risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="b35b5-123">For example, change the column name for the `Name` column to "SomeChild/ModelName" and you will obtain XML with hierarchy, as shown in this result:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="122">`  
  
 `<SomeChild>`  
  
 `<ModelName>All-Purpose Bike Stand</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData id="119">`  
  
 `<SomeChild>`  
  
 `<ModelName>Bike Wash</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="b35b5-124">Oltre all'ID del modello di prodotto e al nome, la query seguente consente di recuperare i percorsi delle relative istruzioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="b35b5-124">Besides the product model ID and name, the following query retrieves the manufacturing instruction locations for the product model.</span></span> <span data-ttu-id="b35b5-125">Poiché la colonna Instructions è di tipo `xml`, per il recupero del percorso viene specificato il metodo `query()` del tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="b35b5-125">Because the Instructions column is of `xml` type, the `query()` method of `xml` data type is specified to retrieve the location.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') AS ManuInstr  
FROM Production.ProductModel  
WHERE ProductModelID = 7  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="b35b5-126">Di seguito è riportato il risultato parziale.</span><span class="sxs-lookup"><span data-stu-id="b35b5-126">This is the partial result.</span></span> <span data-ttu-id="b35b5-127">Poiché la query specifica ManuInstr come nome della colonna, il codice XML restituito dal `query()` metodo viene sottoposta a incapsulamento in un <`ManuInstr`> tag, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b35b5-127">Because the query specifies ManuInstr as the column name, the XML returned by the `query()` method is wrapped in a <`ManuInstr`> tag as shown in the following:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="7">`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<ManuInstr>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `<MI:step>...</MI:step>...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ManuInstr>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="b35b5-128">Nella query FOR XML precedente può essere utile includere gli spazi dei nomi per gli elementi <`Root`> e <`ProductModelData`>.</span><span class="sxs-lookup"><span data-stu-id="b35b5-128">In the previous FOR XML query, you may want to include namespaces for the <`Root`> and <`ProductModelData`> elements.</span></span> <span data-ttu-id="b35b5-129">A questo scopo è necessario innanzitutto definire i prefissi per l'associazione degli spazi dei nomi tramite WITH XMLNAMESPACES e utilizzare tali prefissi nella query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="b35b5-129">You can do this by first defining the prefix to namespace binding by using WITH XMLNAMESPACES and using prefixes in the FOR XML query.</span></span> <span data-ttu-id="b35b5-130">Per altre informazioni, vedere [Aggiungere spazi dei nomi alle query con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b35b5-130">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES (  
   'uri1' AS ns1,    
   'uri2' AS ns2,  
   'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions' as MI)  
SELECT ProductModelID AS "ns1:ProductModelID",  
       Name           AS "ns1:Name",  
       Instructions.query('  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ('ns2:ProductInfo'), root('ns1:root');  
GO  
```  
  
 <span data-ttu-id="b35b5-131">Il prefisso `MI` è inoltre definito in `WITH XMLNAMESPACES`.</span><span class="sxs-lookup"><span data-stu-id="b35b5-131">Note that the `MI` prefix is also defined in the `WITH XMLNAMESPACES`.</span></span> <span data-ttu-id="b35b5-132">Di conseguenza, il metodo `query()` del tipo `xml` specificato non definisce il prefisso nel prologo della query.</span><span class="sxs-lookup"><span data-stu-id="b35b5-132">As a result, the `query()` method of the `xml` type specified does not define the prefix in the query prolog.</span></span> <span data-ttu-id="b35b5-133">Risultato:</span><span class="sxs-lookup"><span data-stu-id="b35b5-133">This is the result:</span></span>  
  
 `<ns1:root xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">`  
  
 `<ns2:ProductInfo>`  
  
 `<ns1:ProductModelID>7</ns1:ProductModelID>`  
  
 `<ns1:Name>HL Touring Frame</ns1:Name>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `LaborHours="2.5" LotSize="100" MachineHours="3" SetupHours="0.5" LocationID="10" xmlns="">`  
  
 `<MI:step>`  
  
 `Insert <MI:material>aluminum sheet MS-2341</MI:material> into the <MI:tool>T-85A framing tool</MI:tool>.`  
  
 `</MI:step>`  
  
 `...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ns2:ProductInfo>`  
  
 `</ns1:root>`  
  
## <a name="generating-a-value-list-using-path-mode"></a><span data-ttu-id="b35b5-134">Creazione di un elenco di valori mediante la modalità PATH</span><span class="sxs-lookup"><span data-stu-id="b35b5-134">Generating a value list using PATH mode</span></span>  
 <span data-ttu-id="b35b5-135">La query successiva crea un elenco di valori di prodotti ID.</span><span class="sxs-lookup"><span data-stu-id="b35b5-135">For each product model, this query constructs a value list of product IDs.</span></span> <span data-ttu-id="b35b5-136">Per ogni ID prodotto la query crea inoltre elementi nidificati <`ProductName`>, come illustrato in questo frammento XML:</span><span class="sxs-lookup"><span data-stu-id="b35b5-136">For each product ID, the query also constructs <`ProductName`> nested elements, as shown in this XML fragment:</span></span>  
  
 `<ProductModelData ProductModelID="7" ProductModelName="..."`  
  
 `ProductIDs="product id list in the product model" >`  
  
 `<ProductName>...</ProductName>`  
  
 `<ProductName>...</ProductName>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="b35b5-137">La query che produce il codice XML desiderato è la seguente:</span><span class="sxs-lookup"><span data-stu-id="b35b5-137">This is the query that produces the XML you want:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID     AS "@ProductModelID",  
       Name               S "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')) S "@ProductIDs",  
       (SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
        FOR XML PATH ('')) as "ProductNames"  
FROM   Production.ProductModel  
WHERE  ProductModelID= 7 or ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="b35b5-138">Dalla query precedente si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b35b5-138">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="b35b5-139">La prima istruzione `SELECT` nidificata restituisce un elenco di ProductID utilizzando il nome di colonna `data()` .</span><span class="sxs-lookup"><span data-stu-id="b35b5-139">The first nested `SELECT` returns a list of ProductIDs by using `data()` as the column name.</span></span> <span data-ttu-id="b35b5-140">Poiché la query specifica una stringa vuota come nome dell'elemento riga in `FOR XML PATH`, non viene generato alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="b35b5-140">Because the query specifies an empty string as the row element name in `FOR XML PATH`, no element is generated.</span></span> <span data-ttu-id="b35b5-141">L'elenco di valori viene invece assegnato all'attributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="b35b5-141">Instead, the value list is assigned to the `ProductID` attribute.</span></span>  
  
-   <span data-ttu-id="b35b5-142">La seconda istruzione `SELECT` nidificata recupera i nomi dei prodotti per quelli presenti nel modello del prodotto.</span><span class="sxs-lookup"><span data-stu-id="b35b5-142">The second nested `SELECT` retrieves product names for products in the product model.</span></span> <span data-ttu-id="b35b5-143">Genera elementi <`ProductName`> che vengono restituiti inseriti nell'elemento <`ProductNames`>, poiché la query specifica `ProductNames` come nome di colonna.</span><span class="sxs-lookup"><span data-stu-id="b35b5-143">It generates <`ProductName`> elements that are returned wrapped in the <`ProductNames`> element, because the query specifies `ProductNames` as the column name.</span></span>  
  
 <span data-ttu-id="b35b5-144">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="b35b5-144">This is the partial result:</span></span>  
  
 `<ProductModelData PId="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>HL Touring Frame - Yellow, 60</ProductName>`  
  
 `<ProductName>HL Touring Frame - Yellow, 46</ProductName></ProductNames>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 `<ProductModelData PId="9"`  
  
 `ProductModelName="LL Road Frame"`  
  
 `ProductIDs="722 723 724 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>LL Road Frame - Black, 58</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 60</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 62</ProductName>`  
  
 `...`  
  
 `</ProductNames>`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="b35b5-145">La sottoquery che crea i nomi di prodotto restituisce il risultato sotto forma di una stringa sostituita con entità e quindi aggiunta al codice XML.</span><span class="sxs-lookup"><span data-stu-id="b35b5-145">The subquery constructing the product names returns the result as a string that is entitized and then added to the XML.</span></span> <span data-ttu-id="b35b5-146">Se si aggiunge la direttiva TYPE, `FOR XML PATH (''), type`, la sottoquery restituisce il risultato come tipo `xml` e non viene eseguita la sostituzione con entità.</span><span class="sxs-lookup"><span data-stu-id="b35b5-146">If you add the type directive, `FOR XML PATH (''), type`, the subquery returns the result as `xml` type and no entitization occurs.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@ProductModelID",  
      Name AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ProductIDs",  
       (  
       SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH (''), type  
       ) AS "ProductNames"  
  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
## <a name="adding-namespaces-in-the-resulting-xml"></a><span data-ttu-id="b35b5-147">Aggiunta degli spazi dei nomi nel codice XML risultante</span><span class="sxs-lookup"><span data-stu-id="b35b5-147">Adding namespaces in the resulting XML</span></span>  
 <span data-ttu-id="b35b5-148">Come descritto in [Aggiungere spazi dei nomi alle query con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), è possibile usare WITH XMLNAMESPACES per includerli nelle query della modalità PATH.</span><span class="sxs-lookup"><span data-stu-id="b35b5-148">As described in [Adding Namespaces Using WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), you can use WITH XMLNAMESPACES to include namespaces in the PATH mode queries.</span></span> <span data-ttu-id="b35b5-149">Ad esempio, i nomi specificati nella clausola SELECT includono i prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b35b5-149">For example, names specified in the SELECT clause include namespace prefixes.</span></span> <span data-ttu-id="b35b5-150">La seguente query in modalità `PATH` crea codice XML con spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b35b5-150">The following `PATH` mode query constructs XML with namespaces.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
GO  
```  
  
 <span data-ttu-id="b35b5-151">L'attributo `@xml:lang` aggiunto all'elemento <`English`> viene definito nello spazio dei nomi xml predefinito.</span><span class="sxs-lookup"><span data-stu-id="b35b5-151">The `@xml:lang` attribute added to the <`English`> element is defined in the predefined xml namespace.</span></span>  
  
 <span data-ttu-id="b35b5-152">Risultato:</span><span class="sxs-lookup"><span data-stu-id="b35b5-152">This is the result:</span></span>  
  
 `<Translation>`  
  
 `<English xml:lang="en">food</English>`  
  
 `<German xml:lang="ger">Essen</German>`  
  
 `</Translation>`  
  
 <span data-ttu-id="b35b5-153">La query seguente è simile a quella dell'esempio C, ma utilizza `WITH XMLNAMESPACES` per includere gli spazi dei nomi nel risultato XML.</span><span class="sxs-lookup"><span data-stu-id="b35b5-153">The following query is similar to example C, except that it uses `WITH XMLNAMESPACES` to include namespaces in the XML result.</span></span> <span data-ttu-id="b35b5-154">Per altre informazioni, vedere [Aggiungere spazi dei nomi alle query con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b35b5-154">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES ('uri1' AS ns1,  DEFAULT 'uri2')  
SELECT ProductModelID AS "@ns1:ProductModelID",  
      Name AS "@ns1:ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ns1:ProductIDs",  
       (  
       SELECT ProductID AS "@ns1:ProductID",   
              Name AS "@ns1:ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH , type   
       ) AS "ns1:ProductNames"  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData'), root('root');  
```  
  
 <span data-ttu-id="b35b5-155">Risultato:</span><span class="sxs-lookup"><span data-stu-id="b35b5-155">This is the result:</span></span>  
  
 `<root xmlns="uri2" xmlns:ns1="uri1">`  
  
 `<ProductModelData ns1:ProductModelID="7" ns1:ProductModelName="HL Touring Frame" ns1:ProductIDs="885 887 888 889 890 891 892 893">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="885" ns1:ProductName="HL Touring Frame - Yellow, 60" />`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="887" ns1:ProductName="HL Touring Frame - Yellow, 46" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData ns1:ProductModelID="9" ns1:ProductModelName="LL Road Frame" ns1:ProductIDs="722 723 724 725 726 727 728 729 730 736 737 738">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="722" ns1:ProductName="LL Road Frame - Black, 58" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `</root>`  
  
## <a name="see-also"></a><span data-ttu-id="b35b5-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b35b5-156">See Also</span></span>  
 [<span data-ttu-id="b35b5-157">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="b35b5-157">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
