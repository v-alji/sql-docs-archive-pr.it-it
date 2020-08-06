---
title: Generare uno schema XSD inline | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- XMLSCHEMA option
- schemas [SQL Server], XML
- XDR schemas
- FOR XML clause, inline XSD schema generation
- inline XSD schema generation [SQL Server]
- XMLDATA option
ms.assetid: 04b35145-1cca-45f4-9eb7-990abf2e647d
author: rothja
ms.author: jroth
ms.openlocfilehash: 2af748d4fc6ae67f57568be58ec7f59876098f52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726752"
---
# <a name="generate-an-inline-xsd-schema"></a><span data-ttu-id="74163-102">Generazione di uno schema XSD inline</span><span class="sxs-lookup"><span data-stu-id="74163-102">Generate an Inline XSD Schema</span></span>
  <span data-ttu-id="74163-103">In una clausola FOR XML è possibile richiedere che la query restituisca uno schema inline oltre ai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="74163-103">In a FOR XML clause, you can request that your query return an inline schema together with the query results.</span></span> <span data-ttu-id="74163-104">Per ottenere uno schema XDR, utilizzare la parola chiave XMLDATA nella clausola FOR XML.</span><span class="sxs-lookup"><span data-stu-id="74163-104">If you want an XDR schema, you use the XMLDATA keyword in the FOR XML clause.</span></span> <span data-ttu-id="74163-105">Per ottenere uno schema XSD, utilizzare invece la parola chiave XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="74163-105">If you want an XSD schema, you use the XMLSCHEMA keyword.</span></span>  
  
 <span data-ttu-id="74163-106">In questo argomento viene descritta la parola chiave XMLSCHEMA e viene illustrata la struttura dello schema XSD risultante.</span><span class="sxs-lookup"><span data-stu-id="74163-106">This topic describes the XMLSCHEMA keyword and explains the structure of the resulting inline XSD schema.</span></span> <span data-ttu-id="74163-107">Di seguito sono illustrate le limitazioni previste per la richiesta di schemi inline:</span><span class="sxs-lookup"><span data-stu-id="74163-107">Following are the limitations when you are requesting inline schemas:</span></span>  
  
-   <span data-ttu-id="74163-108">È possibile specificare la parola chiave XMLSCHEMA unicamente nelle modalità RAW e AUTO e non nella modalità EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="74163-108">You can specify XMLSCHEMA only in RAW and AUTO mode, not in EXPLICIT mode.</span></span>  
  
-   <span data-ttu-id="74163-109">Se in una query FOR XML nidificata è specificata la direttiva TYPE, il risultato della query sarà di tipo `xml` e verrà considerato come un'istanza di dati XML non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="74163-109">If a nested FOR XML query specifies the TYPE directive, the query result is of `xml` type, and this result is treated as an instance of untyped XML data.</span></span> <span data-ttu-id="74163-110">Per altre informazioni, vedere [Dati XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74163-110">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="74163-111">Se si specifica la parola chiave XMLSCHEMA in una query FOR XML, si otterrà sia uno schema che i dati XML, ovvero il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="74163-111">When you specify XMLSCHEMA in a FOR XML query, you receive both a schema and XML data, the query result.</span></span> <span data-ttu-id="74163-112">Ogni elemento di livello principale dei dati fa riferimento allo schema precedente tramite una dichiarazione dello spazio dei nomi predefinito che, a sua volta, fa riferimento allo spazio dei nomi di destinazione dello schema inline.</span><span class="sxs-lookup"><span data-stu-id="74163-112">Each top-level element of the data refers to the previous schema by using a default namespace declaration that, in turn, refers to the target namespace of the inline schema.</span></span>  
  
 <span data-ttu-id="74163-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="74163-113">For example:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks2012].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<Production.ProductModel xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="1" Name="Classic Vest" />  
```  
  
 <span data-ttu-id="74163-114">Il risultato include XML Schema e il risultato XML.</span><span class="sxs-lookup"><span data-stu-id="74163-114">The result includes XML schema and the XML result.</span></span> <span data-ttu-id="74163-115">L'elemento di livello principale <`ProductModel`> nel risultato fa riferimento allo schema tramite la dichiarazione dello spazio dei nomi predefinito, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1".</span><span class="sxs-lookup"><span data-stu-id="74163-115">The <`ProductModel`> top-level element in the result refers to the schema by using the default namespace declaration, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span></span>  
  
 <span data-ttu-id="74163-116">La parte del risultato relativa allo schema può contenere più documenti dello schema che descrivono più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="74163-116">The schema part of the result may contain multiple schema documents that describe multiple namespaces.</span></span> <span data-ttu-id="74163-117">Verranno restituiti almeno i due documenti di schema seguenti:</span><span class="sxs-lookup"><span data-stu-id="74163-117">At a minimum, the following two schema documents are returned:</span></span>  
  
-   <span data-ttu-id="74163-118">Un documento di schema per lo spazio dei nomi **Sqltypes** e per il quale vengono restituiti i tipi SQL di base.</span><span class="sxs-lookup"><span data-stu-id="74163-118">One schema document for the **Sqltypes** namespace, and for which the base SQL types are being returned.</span></span>  
  
-   <span data-ttu-id="74163-119">Un altro documento di schema che descrive la forma del risultato della query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="74163-119">Another schema document that describes the shape of the FOR XML query result.</span></span>  
  
 <span data-ttu-id="74163-120">Se il risultato della query contiene tipi di dati `xml` tipizzati, verranno inclusi anche gli schemi associati a tali tipi di dati `xml` tipizzati.</span><span class="sxs-lookup"><span data-stu-id="74163-120">Also, if any typed `xml` data types are included in the query result, the schemas associated with those typed `xml` data types are included.</span></span>  
  
 <span data-ttu-id="74163-121">Lo spazio dei nomi di destinazione del documento di schema che descrive la forma del risultato della query FOR XML contiene una parte fissa e una parte numerica che viene incrementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="74163-121">The target namespace of the schema document that describes the shape of the FOR XML result contains a fixed portion and a numeric portion that increments automatically.</span></span> <span data-ttu-id="74163-122">Di seguito è illustrato il formato di questo spazio dei nomi, dove *n* è un numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="74163-122">The format of this namespace is shown in the following where *n* is a positive integer.</span></span> <span data-ttu-id="74163-123">Ad esempio, nella query precedente urn:schemas-microsoft-com:sql:SqlRowSet1 rappresenta lo spazio dei nomi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="74163-123">For example, in the previous query, urn:schemas-microsoft-com:sql:SqlRowSet1 is the target namespace.</span></span>  
  
```  
urn:schemas-microsoft-com:sql:SqlRowSetn  
```  
  
 <span data-ttu-id="74163-124">La modifica degli spazi dei nomi di destinazione nel risultato tra un'esecuzione e l'altra non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="74163-124">The change in the target namespaces in the result that occurred from one execution to another may not be desirable.</span></span> <span data-ttu-id="74163-125">Ad esempio, se si esegue una query sul codice XML risultante, tale modifica richiederà l'aggiornamento della query.</span><span class="sxs-lookup"><span data-stu-id="74163-125">For example, if you query the resulting XML, the change in target namespace will require that you update your query.</span></span> <span data-ttu-id="74163-126">Se nella clausola FOR XML viene aggiunta l'opzione XMLSCHEMA, è possibile specificare facoltativamente uno spazio dei nomi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="74163-126">You can optionally specify a target namespace when the XMLSCHEMA option is added in the FOR XML clause.</span></span> <span data-ttu-id="74163-127">Il codice XML risultante includerà lo spazio dei nomi specificato e rimarrà invariato, indipendentemente dal numero di esecuzioni della query.</span><span class="sxs-lookup"><span data-stu-id="74163-127">The resulting XML will include the namespace you provided and will remain the same, regardless of how many times you run the query.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM   Production.ProductModel  
WHERE ProductModelID=1  
FOR XML AUTO, XMLSCHEMA ('MyURI')  
```  
  
## <a name="entity-elements"></a><span data-ttu-id="74163-128">Elementi entità</span><span class="sxs-lookup"><span data-stu-id="74163-128">Entity Elements</span></span>  
 <span data-ttu-id="74163-129">Prima di fornire informazioni dettagliate sulla struttura dello schema XSD generato per il risultato della query, è necessario descrivere l'elemento entità.</span><span class="sxs-lookup"><span data-stu-id="74163-129">In order to discuss the details of the XSD schema structure generated for the query result, the entity element has to first be described</span></span>  
  
 <span data-ttu-id="74163-130">Un elemento entità nel codice XML restituito dalla query FOR XML è un elemento generato da una tabella e non da una colonna.</span><span class="sxs-lookup"><span data-stu-id="74163-130">An entity element in the XML data returned by FOR XML query is an element that is generated from a table and not from a column.</span></span> <span data-ttu-id="74163-131">La query FOR XML seguente, ad esempio, restituisce informazioni relative ai contatti presenti nella tabella `Person` del database `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="74163-131">For example, the following FOR XML query returns contact information from the `Person` table in the `AdventureWorks2012` database.</span></span>  
  
```  
SELECT BusinessEntityID, FirstName  
FROM Person.Person  
WHERE BusinessEntityID = 1  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="74163-132">Risultato:</span><span class="sxs-lookup"><span data-stu-id="74163-132">This is the result:</span></span>  
  
 `<Person>`  
  
 `<BusinessEntityID>1</BusinessEntityID>`  
  
 `<FirstName>Ken</FirstName>`  
  
 `</Person>`  
  
 <span data-ttu-id="74163-133">In questo risultato <`Person`> è l'elemento entità.</span><span class="sxs-lookup"><span data-stu-id="74163-133">In this result, <`Person`> is the entity element.</span></span> <span data-ttu-id="74163-134">Nel risultato XML possono essere presenti più elementi entità, per ognuno dei quali è disponibile una dichiarazione globale nello schema XSD inline.</span><span class="sxs-lookup"><span data-stu-id="74163-134">There can be multiple entity elements in the XML result and each of these has a global declaration in the inline XSD schema.</span></span> <span data-ttu-id="74163-135">Ad esempio, la query seguente recupera l'intestazione e i dettagli relativi a un ordine di vendita specifico.</span><span class="sxs-lookup"><span data-stu-id="74163-135">For example, the following query retrieves sales order header and detail information for a specific order.</span></span>  
  
```  
SELECT  SalesOrderHeader.SalesOrderID, ProductID, OrderQty  
FROM    Sales.SalesOrderHeader, Sales.SalesOrderDetail  
WHERE   SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
AND     SalesOrderHeader.SalesOrderID=5001  
FOR XML AUTO, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="74163-136">Nella query è specificata la direttiva ELEMENTS e pertanto il codice XML risultante è incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="74163-136">Because the query specifies the ELEMENTS directive, the resulting XML is element-centric.</span></span> <span data-ttu-id="74163-137">Nella query è inoltre specificata la direttiva XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="74163-137">The query also specifies the XMLSCHEMA directive.</span></span> <span data-ttu-id="74163-138">e pertanto viene restituito uno schema XSD inline.</span><span class="sxs-lookup"><span data-stu-id="74163-138">Therefore, an inline XSD schema is returned.</span></span> <span data-ttu-id="74163-139">Risultato:</span><span class="sxs-lookup"><span data-stu-id="74163-139">This is the result:</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="Sales.SalesOrderHeader">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="SalesOrderID" type="sqltypes:int" />`  
  
 `<xsd:element ref="schema:Sales.SalesOrderDetail" minOccurs="0" maxOccurs="unbounded" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `<xsd:element name="Sales.SalesOrderDetail">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="OrderQty" type="sqltypes:smallint" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 <span data-ttu-id="74163-140">Dalla query precedente si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="74163-140">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="74163-141">Nel risultato <`SalesOrderHeader`> e <`SalesOrderDetail`> sono elementi entità</span><span class="sxs-lookup"><span data-stu-id="74163-141">In the result, <`SalesOrderHeader`> and <`SalesOrderDetail`> are entity elements.</span></span> <span data-ttu-id="74163-142">e pertanto vengono dichiarati a livello globale nello schema.</span><span class="sxs-lookup"><span data-stu-id="74163-142">Because of this, they are globally declared in the schema.</span></span> <span data-ttu-id="74163-143">Ciò significa che la dichiarazione è presente nel livello principale dell'elemento <`Schema`>.</span><span class="sxs-lookup"><span data-stu-id="74163-143">That is, the declaration appears at the top level inside the <`Schema`> element.</span></span>  
  
-   <span data-ttu-id="74163-144"><`SalesOrderID`>, <`ProductID`> e <`OrderQty`> non sono elementi entità perché è stato eseguito il mapping a colonne.</span><span class="sxs-lookup"><span data-stu-id="74163-144">The <`SalesOrderID`>, <`ProductID`>, and <`OrderQty`> are not entity elements, because they map to columns.</span></span> <span data-ttu-id="74163-145">I dati di colonna vengono restituiti come elementi nel codice XML e ciò è dovuto alla direttiva ELEMENTS.</span><span class="sxs-lookup"><span data-stu-id="74163-145">The column data is returned as elements in the XML, because of the ELEMENTS directive.</span></span> <span data-ttu-id="74163-146">Per tali elementi viene eseguito il mapping a elementi locali del tipo complesso dell'elemento entità.</span><span class="sxs-lookup"><span data-stu-id="74163-146">These are mapped to local elements of the entity element's complex type.</span></span> <span data-ttu-id="74163-147">Si noti che se non viene specificata la direttiva ELEMENTS, per i valori `SalesOrderID`, `ProductID` e `OrderQty` viene eseguito il mapping ad attributi locali del tipo complesso dell'elemento entità corrispondente.</span><span class="sxs-lookup"><span data-stu-id="74163-147">Note that if the ELEMENTS directive is not specified, the `SalesOrderID`, `ProductID` and `OrderQty` values are mapped to local attributes of the corresponding entity element's complex type.</span></span>  
  
## <a name="attribute-name-clashes"></a><span data-ttu-id="74163-148">Conflitti dei nomi di attributi</span><span class="sxs-lookup"><span data-stu-id="74163-148">Attribute Name Clashes</span></span>  
 <span data-ttu-id="74163-149">Le informazioni seguenti si basano sulle tabelle `CustOrder` e `CustOrderDetail` :</span><span class="sxs-lookup"><span data-stu-id="74163-149">The following discussion is based on the `CustOrder` and `CustOrderDetail` tables.</span></span> <span data-ttu-id="74163-150">Per testare gli esempi seguenti, creare le tabelle e inserire dati di esempio personalizzati:</span><span class="sxs-lookup"><span data-stu-id="74163-150">To test the following samples, create these tables and add your own sample data:</span></span>  
  
```  
CREATE TABLE CustOrder (OrderID int primary key, CustomerID int)  
GO  
CREATE TABLE CustOrderDetail (OrderID int, ProductID int, Qty int)  
GO  
```  
  
 <span data-ttu-id="74163-151">Nelle query FOR XML a volte viene utilizzato lo stesso nome per indicare proprietà o attributi diversi.</span><span class="sxs-lookup"><span data-stu-id="74163-151">In FOR XML, the same name is sometimes used to indicate different properties, attributes.</span></span> <span data-ttu-id="74163-152">Ad esempio, la query in modalità RAW incentrata sugli attributi seguente crea due attributi con lo stesso nome, OrderID</span><span class="sxs-lookup"><span data-stu-id="74163-152">For example, the following attribute-centric RAW mode query generates two attributes that have the same name, OrderID.</span></span> <span data-ttu-id="74163-153">e viene quindi generato un errore.</span><span class="sxs-lookup"><span data-stu-id="74163-153">This generates an error.</span></span>  
  
```  
SELECT CustOrder.OrderID,   
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
FROM   dbo.CustOrder, dbo.CustOrderDetail  
WHERE  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA  
```  
  
 <span data-ttu-id="74163-154">Poiché è tuttavia consentito che due elementi abbiano lo stesso nome, è possibile risolvere il problema aggiungendo la direttiva ELEMENTS:</span><span class="sxs-lookup"><span data-stu-id="74163-154">However, because it is acceptable to have two elements that have the same name, you can eliminate the problem by adding the ELEMENTS directive:</span></span>  
  
```  
SELECT CustOrder.OrderID,  
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
from   dbo.CustOrder, dbo.CustOrderDetail  
where  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA, ELEMENTS  
```  
  
 <span data-ttu-id="74163-155">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="74163-155">This is the result.</span></span> <span data-ttu-id="74163-156">Si noti che nello schema XSD inline, l'elemento OrderID è definito due volte.</span><span class="sxs-lookup"><span data-stu-id="74163-156">Note in the inline XSD schema, the OrderID element is defined two times.</span></span> <span data-ttu-id="74163-157">Per una dichiarazione minOccurs è impostato su 0 e corrisponde all'elemento OrderID della tabella CustOrderDetail e la seconda dichiarazione esegue il mapping alla colonna chiave primaria OrderID della tabella `CustOrder` , nella quale minOccurs è 1 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="74163-157">One of the declarations has minOccurs set to 0, corresponding to the OrderID from the CustOrderDetail table, and the second one maps to the OrderID primary key column of the `CustOrder` table where minOccurs is 1 by default.</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" />`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" minOccurs="0" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
## <a name="element-name-clashes"></a><span data-ttu-id="74163-158">Conflitti dei nomi di elementi</span><span class="sxs-lookup"><span data-stu-id="74163-158">Element Name Clashes</span></span>  
 <span data-ttu-id="74163-159">Nelle query FOR XML è possibile utilizzare lo stesso nome per indicare due sottoelementi.</span><span class="sxs-lookup"><span data-stu-id="74163-159">In FOR XML, the same name can be used to indicate two subelements.</span></span> <span data-ttu-id="74163-160">Ad esempio, la query seguente recupera i valori ListPrice e DealerPrice dei prodotti, ma specifica lo stesso alias per le due colonne, ovvero Price.</span><span class="sxs-lookup"><span data-stu-id="74163-160">For example, the following query retrieves ListPrice and DealerPrice values of products, but the query specifies the same alias, Price, for these two columns.</span></span> <span data-ttu-id="74163-161">Nel set di righe risultante saranno pertanto presenti due colonne con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="74163-161">Therefore, the resulting rowset will have two columns with same name.</span></span>  
  
### <a name="case-1-both-subelements-are-nonkey-columns-of-the-same-type-and-can-be-null"></a><span data-ttu-id="74163-162">Caso 1: entrambi i sottoelementi sono colonne non chiave dello stesso tipo e possono essere NULL</span><span class="sxs-lookup"><span data-stu-id="74163-162">Case 1: Both subelements are nonkey columns of the same type and can be NULL</span></span>  
 <span data-ttu-id="74163-163">Nella query seguente, entrambi i sottoelementi sono colonne non chiave dello stesso tipo e possono essere NULL.</span><span class="sxs-lookup"><span data-stu-id="74163-163">In the following query, both subelements are nonkey columns of the same type and can be NULL.</span></span>  
  
```  
DROP TABLE T  
go  
CREATE TABLE T (ProductID int primary key, ListPrice money, DealerPrice money)  
go  
INSERT INTO T values (1, 1.25, null)  
go  
  
SELECT ProductID, ListPrice Price, DealerPrice Price  
FROM   T  
for    XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="74163-164">Di seguito è riportato il codice XML generato,</span><span class="sxs-lookup"><span data-stu-id="74163-164">This is the corresponding XML generated.</span></span> <span data-ttu-id="74163-165">nel quale è visualizzata solo una frazione dello schema XSD inline:</span><span class="sxs-lookup"><span data-stu-id="74163-165">Only a fraction of the inline XSD is shown:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" minOccurs="0" maxOccurs="2" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `</row>`  
  
 <span data-ttu-id="74163-166">Nello schema XSD si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="74163-166">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="74163-167">ListPrice e DealerPrice sono dello stesso tipo, `money`ed entrambi possono essere NULL nella tabella.</span><span class="sxs-lookup"><span data-stu-id="74163-167">Both the ListPrice and DealerPrice are of the same type, `money`, and both can be NULL in the table.</span></span> <span data-ttu-id="74163-168">Dato che non possono essere restituiti nel codice XML risultante, nella dichiarazione del tipo complesso dell'elemento <`row`> esiste pertanto un solo elemento figlio <`Price`> con minOccurs=0 e maxOccurs=2.</span><span class="sxs-lookup"><span data-stu-id="74163-168">Therefore, because they may not be returned in the resulting XML, there is only one <`Price`> child element in the complex type declaration of the <`row`> element that has minOccurs=0 and maxOccurs=2.</span></span>  
  
-   <span data-ttu-id="74163-169">Poiché il valore `DealerPrice` è NULL nella tabella, nel risultato viene restituito solo `ListPrice` come elemento <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="74163-169">In the result, because the `DealerPrice` value is NULL in the table, only `ListPrice` is returned as a <`Price`> element.</span></span> <span data-ttu-id="74163-170">Se si aggiunge il parametro `XSINIL` alla direttiva ELEMENTS, si otterranno entrambi gli elementi con il valore `xsi:nil` impostato su TRUE per l'elemento <`Price`> corrispondente a DealerPrice.</span><span class="sxs-lookup"><span data-stu-id="74163-170">If you add the `XSINIL` parameter to the ELEMENTS directive, you will receive both of the elements that have the `xsi:nil` value set to TRUE for the<`Price`> element that corresponds to DealerPrice.</span></span> <span data-ttu-id="74163-171">Si otterranno inoltre due elementi figlio <`Price`> nella definizione del tipo complesso <`row`> dello schema XSD inline, con l'attributo `nillable` impostato su TRUE per entrambi.</span><span class="sxs-lookup"><span data-stu-id="74163-171">You will also receive two <`Price`> child elements in the <`row`> complex type definition in the inline XSD schema with the `nillable` attribute set to TRUE for both.</span></span> <span data-ttu-id="74163-172">Di seguito è riportato un frammento che rappresenta un risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="74163-172">This fragment is a partial result:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `<Price xsi:nil="true" />`  
  
 `</row>`  
  
### <a name="case-2-one-key-and-one-nonkey-column-of-the-same-type"></a><span data-ttu-id="74163-173">Caso 2: una colonna chiave e una colonna non chiave dello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="74163-173">Case 2: One key and one nonkey column of the same type</span></span>  
 <span data-ttu-id="74163-174">La query seguente illustra una colonna chiave e una colonna non chiave dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="74163-174">The following query illustrates one key and one nonkey column of the same type.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 int, Col3 nvarchar(20))  
go  
INSERT INTO T VALUES (1, 1, 'test')  
go   
```  
  
 <span data-ttu-id="74163-175">La query seguente alla tabella **T** specifica lo stesso alias per Col1 e Col2, dove Col1 è una chiave primaria e non può essere Null e Col2 può essere Null.</span><span class="sxs-lookup"><span data-stu-id="74163-175">The following query against table **T** specifies the same alias for Col1 and Col2, where Col1 is a primary key and cannot be null, and Col2 can be null.</span></span> <span data-ttu-id="74163-176">Vengono pertanto generati due elementi di pari livello che sono figli dell'elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="74163-176">This generates two sibling elements that are children of the <`row`> element.</span></span>  
  
```  
SELECT Col1 as Col, Col2 as Col, Col3  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="74163-177">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="74163-177">This is the result.</span></span> <span data-ttu-id="74163-178">nel quale è visualizzato solo un frammento dello schema XSD inline.</span><span class="sxs-lookup"><span data-stu-id="74163-178">Only a fragment of the inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="Col3" minOccurs="0">`  
  
 `<xsd:simpleType>`  
  
 `<xsd:restriction base="sqltypes:nvarchar"`  
  
 `sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth"`  
  
 `sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `</xsd:element>`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col>1</Col>`  
  
 `<Col>1</Col>`  
  
 `<Col3>test</Col3>`  
  
 `</row>`  
  
 <span data-ttu-id="74163-179">Si noti che per l'elemento <`Col`> dello schema XSD inline, minOccurs è impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="74163-179">Note in the inline XSD schema that the <`Col`> element corresponding to the Col2 has minOccurs set to 0.</span></span>  
  
### <a name="case-3-both-elements-of-different-types-and-corresponding-columns-can-be-null"></a><span data-ttu-id="74163-180">Caso 3: entrambi gli elementi sono di tipo diverso e le colonne corrispondenti possono essere NULL</span><span class="sxs-lookup"><span data-stu-id="74163-180">Case 3: Both elements of different types and corresponding columns can be NULL</span></span>  
 <span data-ttu-id="74163-181">La query seguente viene eseguita sulla tabella di esempio illustrata nel caso 2:</span><span class="sxs-lookup"><span data-stu-id="74163-181">The following query is specified against the sample table shown in case 2:</span></span>  
  
```  
SELECT Col1, Col2 as Col, Col3 as Col  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="74163-182">Nella query seguente, a Col2 e Col3 sono assegnati gli stessi alias.</span><span class="sxs-lookup"><span data-stu-id="74163-182">In the following query, Col2 and Col3 are given the same aliases.</span></span> <span data-ttu-id="74163-183">Nel risultato vengono pertanto generati due elementi di pari livello con lo stesso nome ed entrambi figli dell'elemento <`raw`>.</span><span class="sxs-lookup"><span data-stu-id="74163-183">This generates two sibling elements that have the same name and that are both children of the <`raw`> element in the result.</span></span> <span data-ttu-id="74163-184">Entrambe le colonne sono di tipo diverso e possono essere NULL.</span><span class="sxs-lookup"><span data-stu-id="74163-184">Both of these columns are of different types and both can be NULL.</span></span> <span data-ttu-id="74163-185">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="74163-185">This is the result.</span></span> <span data-ttu-id="74163-186">nel quale è visualizzato solo uno schema XSD inline parziale.</span><span class="sxs-lookup"><span data-stu-id="74163-186">Only partial inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:simpleType name="Col1">`  
  
 `<xsd:restriction base="sqltypes:int" />`  
  
 `</xsd:simpleType>`  
  
 `<xsd:simpleType name="Col2">`  
  
 `<xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col1" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" minOccurs="0" maxOccurs="2" type="xsd:anySimpleType" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col1>1</Col1>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col1">1</Col>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col2">test</Col>`  
  
 `</row>`  
  
 <span data-ttu-id="74163-187">Nello schema XSD si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="74163-187">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="74163-188">Col2 e Col3 possono entrambe essere NULL e pertanto nella dichiarazione dell'elemento <`Col`> è specificato che minOccurs è 0 e maxOccurs è 2.</span><span class="sxs-lookup"><span data-stu-id="74163-188">Because both Col2 and Col3 can be NULL, the <`Col`> element declaration specifies the minOccurs as 0 and maxOccurs as 2.</span></span>  
  
-   <span data-ttu-id="74163-189">Poiché gli elementi <`Col`> sono di pari livello, nello schema è presente una singola dichiarazione di elemento.</span><span class="sxs-lookup"><span data-stu-id="74163-189">Because both the <`Col`> elements are siblings, there is one element declaration in the schema.</span></span> <span data-ttu-id="74163-190">Inoltre, dato che entrambi gli elementi sono anche di tipo diverso, benché di tipo semplice, il tipo dell'elemento nello schema è `xsd:anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="74163-190">Also, because both of the elements are also of different types, though both are simple types, the type of the element in the schema is `xsd:anySimpleType`.</span></span> <span data-ttu-id="74163-191">Nel risultato, ogni tipo di istanza è identificato dall'attributo `xsi:type` .</span><span class="sxs-lookup"><span data-stu-id="74163-191">In the result, each instance type is identified by the `xsi:type` attribute.</span></span>  
  
-   <span data-ttu-id="74163-192">Nel risultato, ogni istanza dell'elemento <`Col`> fa riferimento al proprio tipo di istanza con l'attributo `xsi:type`.</span><span class="sxs-lookup"><span data-stu-id="74163-192">In the result, every instance of the <`Col`> element refers to its instance type by using the `xsi:type` attribute.</span></span>  
  
  
