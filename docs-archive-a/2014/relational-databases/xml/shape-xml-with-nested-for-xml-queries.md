---
title: Determinare la struttura dei valori XML tramite query FOR XML annidate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], nested FOR XML
- XML [SQL Server], FOR XML queries
ms.assetid: 8dc42c05-16e8-4b7b-a5d3-550b55acae26
author: rothja
ms.author: jroth
ms.openlocfilehash: 738b5b3ec67dada90c851d284ccc8b3009a51aa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630382"
---
# <a name="shape-xml-with-nested-for-xml-queries"></a><span data-ttu-id="a3e0c-102">Determinare la struttura dei valori XML tramite query nidificate FOR XML</span><span class="sxs-lookup"><span data-stu-id="a3e0c-102">Shape XML with Nested FOR XML Queries</span></span>
  <span data-ttu-id="a3e0c-103">Nell'esempio seguente viene eseguita una query sulla tabella `Production.Product` per recuperare i valori di `ListPrice` e `StandardCost` di un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="a3e0c-103">The following example queries the `Production.Product` table to retrieve the `ListPrice` and `StandardCost` values of a specific product.</span></span> <span data-ttu-id="a3e0c-104">Per rendere la query più interessante, entrambi i prezzi vengono restituiti in un elemento <`Price`> e ogni elemento <`Price`> include un attributo `PriceType`.</span><span class="sxs-lookup"><span data-stu-id="a3e0c-104">To make the query interesting, both prices are returned in a <`Price`> element, and each <`Price`> element has a `PriceType` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3e0c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3e0c-105">Example</span></span>  
 <span data-ttu-id="a3e0c-106">La struttura prevista del valore XML è la seguente:</span><span class="sxs-lookup"><span data-stu-id="a3e0c-106">This is the expected shape of the XML:</span></span>  
  
```  
<xsd:schema xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet2" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet2" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.Product" type="xsd:anyType" />  
</xsd:schema>  
<Production.Product xmlns="urn:schemas-microsoft-com:sql:SqlRowSet2" ProductID="520">  
  <Price xmlns="" PriceType="ListPrice">133.34</Price>  
  <Price xmlns="" PriceType="StandardCost">98.77</Price>  
</Production.Product>  
```  
  
 <span data-ttu-id="a3e0c-107">La query FOR XML nidificata è la seguente:</span><span class="sxs-lookup"><span data-stu-id="a3e0c-107">This is the nested FOR XML query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Product.ProductID,   
          (SELECT 'ListPrice' as PriceType,   
                   CAST(CAST(ListPrice as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE),  
          (SELECT  'StandardCost' as PriceType,   
                   CAST(CAST(StandardCost as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE)  
FROM Production.Product  
WHERE ProductID=520  
for XML AUTO, TYPE, XMLSCHEMA  
```  
  
 <span data-ttu-id="a3e0c-108">Dalla query precedente si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a3e0c-108">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="a3e0c-109">L'istruzione SELECT esterna costruisce l'elemento <`Product`>, che ha un attributo **ProductID** e due elementi <`Price`> figlio.</span><span class="sxs-lookup"><span data-stu-id="a3e0c-109">The outer SELECT statement constructs the <`Product`> element that has a **ProductID** attribute and two <`Price`> child elements.</span></span>  
  
-   <span data-ttu-id="a3e0c-110">Le due istruzioni SELECT interne costruiscono due elementi <`Price`>, ognuno con un attributo **PriceType** e un valore XML che restituisce il prezzo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3e0c-110">The two inner SELECT statements construct two <`Price`> elements, each with a **PriceType** attribute and XML that returns the product price.</span></span>  
  
-   <span data-ttu-id="a3e0c-111">La direttiva XMLSCHEMA nell'istruzione SELECT più esterna genera lo schema XSD inline che descrive la struttura del valore XML risultante.</span><span class="sxs-lookup"><span data-stu-id="a3e0c-111">The XMLSCHEMA directive in the outer SELECT statement generates the inline XSD schema that describes the shape of the resulting XML.</span></span>  
  
 <span data-ttu-id="a3e0c-112">Per rendere la query più interessante, è possibile creare la query FOR XML e quindi creare una query XQuery sul risultato in modo da modificare la struttura del valore XML, come illustrato nella query seguente:</span><span class="sxs-lookup"><span data-stu-id="a3e0c-112">To make the query interesting, you can write the FOR XML query and then write an XQuery against the result to reshape the XML, as shown in the following query:</span></span>  
  
```  
SELECT ProductID,   
 ( SELECT p2.ListPrice, p2.StandardCost  
   FROM Production.Product p2   
   WHERE Product.ProductID = p2.ProductID  
   FOR XML AUTO, ELEMENTS XSINIL, type ).query('  
                                   for $p in /p2/*  
                                   return   
                                    <Price PriceType = "{local-name($p)}">  
                                     { data($p) }  
                                    </Price>  
                                  ')  
FROM Production.Product  
WHERE ProductID = 520  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="a3e0c-113">Nell'esempio precedente viene utilizzato il metodo `query()` con tipo di dati `xml` per eseguire una query sul valore XML restituito dalla query FOR XML interna e costruire il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="a3e0c-113">The previous example uses the `query()` method of the `xml` data type to query the XML returned by the inner FOR XML query and construct the expected result.</span></span>  
  
 <span data-ttu-id="a3e0c-114">Risultato:</span><span class="sxs-lookup"><span data-stu-id="a3e0c-114">This is the result:</span></span>  
  
```  
<Production.Product ProductID="520">  
  <Price PriceType="ListPrice">133.3400</Price>  
  <Price PriceType="StandardCost">98.7700</Price>  
</Production.Product>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3e0c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3e0c-115">See Also</span></span>  
 [<span data-ttu-id="a3e0c-116">Utilizzo di query FOR XML nidificate</span><span class="sxs-lookup"><span data-stu-id="a3e0c-116">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
