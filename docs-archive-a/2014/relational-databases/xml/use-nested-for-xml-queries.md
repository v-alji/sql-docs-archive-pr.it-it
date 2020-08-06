---
title: Usare query FOR XML annidate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], nested FOR XML
- nested FOR XML queries
ms.assetid: 7604161a-a958-446d-b102-7dee432979d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 60c4198697f8d19c9b2e5bc1b415e0787861d40a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722600"
---
# <a name="use-nested-for-xml-queries"></a><span data-ttu-id="ec25f-102">Utilizzo di query FOR XML nidificate</span><span class="sxs-lookup"><span data-stu-id="ec25f-102">Use Nested FOR XML Queries</span></span>
  <span data-ttu-id="ec25f-103">Il `xml` tipo di dati e la [direttiva TYPE nelle query for XML](type-directive-in-for-xml-queries.md) consentono l'elaborazione del codice XML restituito dalle query for XML sul server e sul client.</span><span class="sxs-lookup"><span data-stu-id="ec25f-103">The `xml` data type and the [TYPE directive in FOR XML queries](type-directive-in-for-xml-queries.md) enable the XML returned by the FOR XML queries to be processed on the server as well as on the client.</span></span>  
  
## <a name="processing-with-xml-type-variables"></a><span data-ttu-id="ec25f-104">Elaborazione con variabili di tipo XML</span><span class="sxs-lookup"><span data-stu-id="ec25f-104">Processing with xml Type Variables</span></span>  
 <span data-ttu-id="ec25f-105">È possibile assegnare il risultato di una query FOR XML a una variabile di tipo `xml` oppure utilizzare XQuery per eseguire query sul risultato, quindi assegnare tale risultato a una variabile di tipo `xml` per un'ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="ec25f-105">You can assign the FOR XML query result to an `xml` type variable, or use XQuery to query the result, and assign that result to an `xml` type variable for more processing.</span></span>  
  
```  
DECLARE @x xml  
SET @x=(SELECT ProductModelID, Name  
        FROM Production.ProductModel  
        WHERE ProductModelID=122 or ProductModelID=119  
        FOR XML RAW, TYPE)  
SELECT @x  
-- Result  
--<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
--<row ProductModelID="119" Name="Bike Wash" />  
```  
  
 <span data-ttu-id="ec25f-106">Il valore XML restituito nella variabile `@x` può essere ulteriormente elaborato utilizzando uno dei metodi con tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="ec25f-106">You can additionally process the XML returned in the variable, `@x`, by using one of the `xml` data type methods.</span></span> <span data-ttu-id="ec25f-107">Ad esempio, è possibile recuperare il valore dell'attributo `ProductModelID` usando il [metodo value()](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="ec25f-107">For example, you can retrieve the `ProductModelID` attribute value by using the [value() method](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
DECLARE @i int;  
SET @i = (SELECT @x.value('/row[1]/@ProductModelID[1]', 'int'));  
SELECT @i;  
```  
  
 <span data-ttu-id="ec25f-108">Nell'esempio seguente il risultato della query `FOR XML` viene restituito come tipo `xml`, perché nella clausola `TYPE` è specificata la direttiva `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="ec25f-108">In the following example, the `FOR XML` query result is returned as an `xml` type, because the `TYPE` directive is specified in the `FOR XML` clause.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=119 or ProductModelID=122  
FOR XML RAW, TYPE,ROOT('myRoot');  
  
```  
  
 <span data-ttu-id="ec25f-109">Risultato:</span><span class="sxs-lookup"><span data-stu-id="ec25f-109">This is the result:</span></span>  
  
```  
<myRoot>  
  <row ProductModelID="122" Name="All-Purpose Bike Stand" />  
  <row ProductModelID="119" Name="Bike Wash" />  
</myRoot>  
```  
  
 <span data-ttu-id="ec25f-110">Poiché il risultato è di tipo `xml`, è possibile applicare uno dei metodi con tipo di dati `xml` direttamente al valore XML, come illustrato nella query seguente.</span><span class="sxs-lookup"><span data-stu-id="ec25f-110">Because the result is of `xml` type, you can specify one of the `xml` data type methods directly against this XML, as shown in the following query.</span></span> <span data-ttu-id="ec25f-111">Nella query viene usato il [metodo query() con tipo di dati XML](/sql/t-sql/xml/query-method-xml-data-type) per recuperare il primo elemento <`row`> figlio dell'elemento <`myRoot`>.</span><span class="sxs-lookup"><span data-stu-id="ec25f-111">In the query, the [query() method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) is used to retrieve the first <`row`> element child of the <`myRoot`> element.</span></span>  
  
```  
SELECT  (SELECT ProductModelID, Name  
         FROM Production.ProductModel  
         WHERE ProductModelID=119 or ProductModelID=122  
         FOR XML RAW, TYPE,ROOT('myRoot')).query('/myRoot[1]/row[1]');  
  
```  
  
 <span data-ttu-id="ec25f-112">Risultato:</span><span class="sxs-lookup"><span data-stu-id="ec25f-112">This is the result:</span></span>  
  
```  
<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
```  
  
## <a name="returning-inner-for-xml-query-results-to-outer-queries-as-xml-type-instances"></a><span data-ttu-id="ec25f-113">Restituzione di risultati della query FOR XML interna a query esterne come istanze di tipo XML</span><span class="sxs-lookup"><span data-stu-id="ec25f-113">Returning Inner FOR XML Query Results to Outer Queries as xml Type Instances</span></span>  
 <span data-ttu-id="ec25f-114">È possibile scrivere query `FOR XML` nidificate in cui il risultato della query interna viene restituito alla query esterna come tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="ec25f-114">You can write nested `FOR XML` queries where the result of the inner query is returned as an `xml` type to the outer query.</span></span> <span data-ttu-id="ec25f-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec25f-115">For example:</span></span>  
  
```  
SELECT Col1,   
       Col2,   
       ( SELECT Col3, Col4   
        FROM  T2  
        WHERE T2.Col = T1.Col  
        ...  
        FOR XML AUTO, TYPE )  
FROM T1  
WHERE ...  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="ec25f-116">Dalla query precedente si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ec25f-116">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="ec25f-117">Il valore XML generato dalla query `FOR XML` interna viene aggiunto al valore XML generato dalla query `FOR XML`esterna.</span><span class="sxs-lookup"><span data-stu-id="ec25f-117">The XML generated by the inner `FOR XML` query is added to the XML generated by the outer `FOR XML`.</span></span>  
  
-   <span data-ttu-id="ec25f-118">Nella query interna viene specificata la direttiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="ec25f-118">The inner query specifies the `TYPE` directive.</span></span> <span data-ttu-id="ec25f-119">I dati restituiti dalla query interna sono pertanto di tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="ec25f-119">Therefore, the XML data returned by the inner query is of `xml` type.</span></span> <span data-ttu-id="ec25f-120">Se non si specifica la direttiva TYPE, il risultato della query `FOR XML` interna viene restituito come `nvarchar(max)` e i dati XML vengono sostituiti con entità.</span><span class="sxs-lookup"><span data-stu-id="ec25f-120">If the TYPE directive is not specified, the result of the inner `FOR XML` query is returned as `nvarchar(max)` and the XML data is entitized.</span></span>  
  
## <a name="controlling-the-shape-of-resulting-xml-data"></a><span data-ttu-id="ec25f-121">Controllo della forma dei dati XML risultanti</span><span class="sxs-lookup"><span data-stu-id="ec25f-121">Controlling the Shape of Resulting XML Data</span></span>  
 <span data-ttu-id="ec25f-122">Le query FOR XML nidificate consentono di avere un maggior controllo nella definizione della forma dei dati XML risultanti.</span><span class="sxs-lookup"><span data-stu-id="ec25f-122">Nested FOR XML queries give you more control in defining the shape of the resulting XML data.</span></span> <span data-ttu-id="ec25f-123">È possibile utilizzare query FOR XML nidificate per costruire valori XML che siano parzialmente incentrati sugli attributi e parzialmente sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="ec25f-123">You can use nested FOR XML queries to construct XML that is partly attribute-centric and partly element-centric.</span></span>  
  
 <span data-ttu-id="ec25f-124">Per altre informazioni su come specificare valori XML incentrati sia sugli attributi sia sugli elementi con query FOR XML nidificate, vedere [Query FOR XML e query nidificata FOR XML a confronto](../xml/for-xml-query-compared-to-nested-for-xml-query.md) e [Determinare la struttura dei valori XML tramite query nidificate FOR XML](../xml/shape-xml-with-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ec25f-124">For more information about specifying both attribute-centric and element-centric XML with nested FOR XML queries, see [FOR XML Query Compared to Nested FOR XML Query](../xml/for-xml-query-compared-to-nested-for-xml-query.md) and [Shape XML with Nested FOR XML Queries](../xml/shape-xml-with-nested-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="ec25f-125">È possibile generare gerarchie XML che includono elementi di pari livello eseguendo query FOR XML nidificate in modalità AUTO.</span><span class="sxs-lookup"><span data-stu-id="ec25f-125">You can generate XML hierarchies that include siblings by specifying nested AUTO mode FOR XML queries.</span></span> <span data-ttu-id="ec25f-126">Per altre informazioni, vedere [Generare elementi di pari livello tramite query nidificate in modalità AUTO](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="ec25f-126">For more information, see [Generate Siblings with a Nested AUTO Mode Query](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span></span>  
  
 <span data-ttu-id="ec25f-127">Indipendentemente dalla modalità utilizzata, le query FOR XML nidificate consentono un maggior controllo nella definizione della forma dei valori XML risultanti</span><span class="sxs-lookup"><span data-stu-id="ec25f-127">Regardless of which mode you use, nested FOR XML queries provide more control in describing the shape of the resulting XML.</span></span> <span data-ttu-id="ec25f-128">e possono essere utilizzate in sostituzione delle query in modalità EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="ec25f-128">They can be used in the place of EXPLICIT mode queries.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ec25f-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="ec25f-129">Examples</span></span>  
 <span data-ttu-id="ec25f-130">Negli argomenti seguenti vengono forniti esempi di query FOR XML nidificate.</span><span class="sxs-lookup"><span data-stu-id="ec25f-130">The following topics provide examples of nested FOR XML queries.</span></span>  
  
 [<span data-ttu-id="ec25f-131">Query FOR XML e query FOR XML annidate a confronto</span><span class="sxs-lookup"><span data-stu-id="ec25f-131">FOR XML Query Compared to Nested FOR XML Query</span></span>](../xml/for-xml-query-compared-to-nested-for-xml-query.md)  
 <span data-ttu-id="ec25f-132">Confronto di una query FOR XML con un solo livello con una query FOR XML nidificata.</span><span class="sxs-lookup"><span data-stu-id="ec25f-132">Compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="ec25f-133">In questo esempio è inclusa una dimostrazione di come specificare valori XML incentrati sia sugli attributi sia sugli elementi come risultato della query.</span><span class="sxs-lookup"><span data-stu-id="ec25f-133">This example includes a demonstration of how to specify both attribute-centric and element-centric XML as the result of the query.</span></span>  
  
 [<span data-ttu-id="ec25f-134">Generare elementi di pari livello tramite query annidate in modalità AUTO</span><span class="sxs-lookup"><span data-stu-id="ec25f-134">Generate Siblings with a Nested AUTO Mode Query</span></span>](../xml/generate-siblings-with-a-nested-auto-mode-query.md)  
 <span data-ttu-id="ec25f-135">Procedura di generazione di elementi di pari livello tramite query nidificate in modalità AUTO</span><span class="sxs-lookup"><span data-stu-id="ec25f-135">Shows how to generate siblings by using a nested AUTO mode query</span></span>  
  
 [<span data-ttu-id="ec25f-136">Usare query FOR XML annidate in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ec25f-136">Use Nested FOR XML Queries in ASP.NET</span></span>](use-nested-for-xml-queries-in-asp-net.md)  
 <span data-ttu-id="ec25f-137">Dimostrazione del modo in cui un'applicazione ASPX può utilizzare FOR XML per restituire XML da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec25f-137">Demonstrates how an ASPX application can use FOR XML to return XML from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ec25f-138">Determinare la struttura dei valori XML tramite query FOR XML annidate</span><span class="sxs-lookup"><span data-stu-id="ec25f-138">Shape XML with Nested FOR XML Queries</span></span>](../xml/shape-xml-with-nested-for-xml-queries.md)  
 <span data-ttu-id="ec25f-139">Utilizzo di query FOR XML nidificate per controllare la struttura di un documento XML creato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec25f-139">Shows how to use nested FOR XML queries to control the structure of an XML document created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
