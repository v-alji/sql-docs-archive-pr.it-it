---
title: 'Esempio: specifica della direttiva HIDE | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- HIDE directive
ms.assetid: 87504d87-1cbd-412a-9041-47884b6efcec
author: rothja
ms.author: jroth
ms.openlocfilehash: 423ee36f679467c07a604b9754172f6e261971b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636605"
---
# <a name="example-specifying-the-hide-directive"></a><span data-ttu-id="a27a6-102">Esempio: specifica della direttiva HIDE</span><span class="sxs-lookup"><span data-stu-id="a27a6-102">Example: Specifying the HIDE Directive</span></span>
  <span data-ttu-id="a27a6-103">Nell'esempio seguente viene illustrato l'utilizzo della direttiva **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="a27a6-103">This example illustrates the use of the **HIDE** directive.</span></span> <span data-ttu-id="a27a6-104">Questa direttiva si rivela utile quando si desidera la restituzione di un attributo in base al quale ordinare le righe nella tabella universale restituita dalla query, ma non si desidera che tale attributo venga visualizzato nel documento XML finale.</span><span class="sxs-lookup"><span data-stu-id="a27a6-104">This directive is useful when you want the query to return an attribute for ordering the rows in the universal table that is returned by the query, but you do not want that attribute in the final resulting XML document.</span></span>  
  
 <span data-ttu-id="a27a6-105">La query genera il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="a27a6-105">This query constructs this XML:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
           <Summary> element from XML stored in CatalogDescription column  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="a27a6-106">Questa query genera il codice XML desiderato.</span><span class="sxs-lookup"><span data-stu-id="a27a6-106">This query generates the XML you want.</span></span> <span data-ttu-id="a27a6-107">La query identifica due gruppi di colonne con valori di Tag 1 e 2 nei nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="a27a6-107">The query identifies two column groups having 1 and 2 as Tag values in the column names.</span></span>  
  
 <span data-ttu-id="a27a6-108">Questa query usa il metodo [query() (tipo di dati xml)](/sql/t-sql/xml/query-method-xml-data-type) del tipo di dati **xml** per eseguire query sulla colonna CatalogDescription di tipo **xml** e recuperare la descrizione di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="a27a6-108">This query uses the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) of the **xml** data type to query the CatalogDescription column of **xml** type in order to retrieve the summary description.</span></span> <span data-ttu-id="a27a6-109">La query usa anche il [metodo value() (tipo di dati xml)](/sql/t-sql/xml/value-method-xml-data-type) del tipo di dati **xml** per il recupero del valore ProductModelID dalla colonna CatalogDescription.</span><span class="sxs-lookup"><span data-stu-id="a27a6-109">The query also uses the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) of the **xml** data type to retrieve the ProductModelID value from the CatalogDescription column.</span></span> <span data-ttu-id="a27a6-110">Questo valore non è necessario nel codice XML risultante, ma lo è per ordinare il set di righe risultante.</span><span class="sxs-lookup"><span data-stu-id="a27a6-110">This value is not required in the resulting XML, but is required to sort the resulting rowset.</span></span> <span data-ttu-id="a27a6-111">Pertanto, il nome della colonna, `[Summary!2!ProductModelID!HIDE]`include la direttiva **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="a27a6-111">Therefore, the column name, `[Summary!2!ProductModelID!HIDE]`, includes the **HIDE** directive.</span></span> <span data-ttu-id="a27a6-112">Se questa colonna non viene inclusa nell'istruzione SELECT sarà necessario ordinare il set di righe per `[ProductModel!1!ProdModelID]` e `[Summary!2!SummaryDescription]` che sono di tipo **xml** e non sarà possibile utilizzare la colonna di tipo **xml** in ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="a27a6-112">If this column is not included in the SELECT statement, you will have to sort the rowset by `[ProductModel!1!ProdModelID]` and `[Summary!2!SummaryDescription]` that is **xml** type and you cannot use the **xml** type column in ORDER BY.</span></span> <span data-ttu-id="a27a6-113">Viene pertanto aggiunta la colonna `[Summary!2!ProductModelID!HIDE]` , che viene poi specificata nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="a27a6-113">Therefore, the additional `[Summary!2!ProductModelID!HIDE]` column is added and is then specified in the ORDER BY clause.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID     as [ProductModel!1!ProdModelID],  
        Name               as [ProductModel!1!Name],  
        NULL               as [Summary!2!ProductModelID!hide],  
        NULL               as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
        CatalogDescription.value('  
         declare namespace PD="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
       (/PD:ProductDescription/@ProductModelID)[1]', 'int'),  
        CatalogDescription.query('  
         declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
         /pd:ProductDescription/pd:Summary')  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],[Summary!2!ProductModelID!hide]  
FOR XML EXPLICIT  
go  
```  
  
 <span data-ttu-id="a27a6-114">Risultato:</span><span class="sxs-lookup"><span data-stu-id="a27a6-114">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <pd:Summary xmlns:pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription" xmlns="">  
        <p1:p xmlns:p1="http://www.w3.org/1999/xhtml">Our top-of-the-line competition mountain bike. Performance-enhancing options include the innovative HL Frame, super-smooth front suspension, and traction for all terrain. </p1:p>  
      </pd:Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a27a6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a27a6-115">See Also</span></span>  
 [<span data-ttu-id="a27a6-116">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="a27a6-116">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
