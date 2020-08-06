---
title: 'Esempio: Creazione di elementi di pari livello con la modalità EXPLICIT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- EXPLICIT FOR XML mode
ms.assetid: 8a57b765-a890-46a3-8b5f-5754e921ea6e
author: rothja
ms.author: jroth
ms.openlocfilehash: 6fe3cecd314772829d9819d42484194f415219a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623935"
---
# <a name="example-constructing-siblings-with-explicit-mode"></a><span data-ttu-id="77ecc-102">Esempio: Creazione di elementi di pari livello con la modalità EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="77ecc-102">Example: Constructing Siblings with EXPLICIT Mode</span></span>
  <span data-ttu-id="77ecc-103">Si supponga di voler creare codice XML per fornire informazioni sugli ordini di vendita.</span><span class="sxs-lookup"><span data-stu-id="77ecc-103">Assume that you want to construct XML that provides sales order information.</span></span> <span data-ttu-id="77ecc-104"><`SalesPerson`> e <`OrderDetail`> sono elementi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="77ecc-104">Note that <`SalesPerson`> and <`OrderDetail`> elements are siblings.</span></span> <span data-ttu-id="77ecc-105">Ogni ordine dispone di un elemento <`OrderHeader`>, un elemento <`SalesPerson`> e uno o più elementi <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="77ecc-105">Each Order has one <`OrderHeader`> element, one <`SalesPerson`> element, and one or more <`OrderDetail`> elements.</span></span>  
  
```  
<OrderHeader SalesOrderID=... OrderDate=... CustomerID=... >  
  <SalesPerson SalesPersonID=... />  
  <OrderDetail SalesOrderID=... LineTotal=... ProductID=... OrderQty=... />  
  <OrderDetail SalesOrderID=... LineTotal=... ProductID=... OrderQty=.../>  
      ...  
</OrderHeader>  
<OrderHeader ...</OrderHeader>  
```  
  
 <span data-ttu-id="77ecc-106">La query in modalità EXPLICIT genera questo codice XML.</span><span class="sxs-lookup"><span data-stu-id="77ecc-106">The following EXPLICIT mode query constructs this XML.</span></span> <span data-ttu-id="77ecc-107">La query specifica valori di `Tag` pari a 1 per l'elemento <`OrderHeader`>, pari a 2 per l'elemento <`SalesPerson`> e pari a 3 per l'elemento <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="77ecc-107">Note that the query specifies `Tag` values of 1 for the <`OrderHeader`> element, 2 for the <`SalesPerson`> element, and 3 for the <`OrderDetail`> element.</span></span> <span data-ttu-id="77ecc-108">Poiché <`SalesPerson`> e <`OrderDetail`> sono elementi di pari livello, la query specifica lo stesso valore di tag `Parent` pari a 1 per l'identificazione dell'elemento <`OrderHeader`>.</span><span class="sxs-lookup"><span data-stu-id="77ecc-108">Because <`SalesPerson`> and <`OrderDetail`> are siblings, the query specifies the same `Parent` tag value of 1 identifying the <`OrderHeader`> element.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        SalesOrderID  as [OrderHeader!1!SalesOrderID],  
        OrderDate     as [OrderHeader!1!OrderDate],  
        CustomerID    as [OrderHeader!1!CustomerID],  
        NULL          as [SalesPerson!2!SalesPersonID],  
        NULL          as [OrderDetail!3!SalesOrderID],  
        NULL          as [OrderDetail!3!LineTotal],  
        NULL          as [OrderDetail!3!ProductID],  
        NULL          as [OrderDetail!3!OrderQty]  
FROM   Sales.SalesOrderHeader  
WHERE     SalesOrderID=43659 or SalesOrderID=43661  
UNION ALL   
SELECT 2 as Tag,  
       1 as Parent,  
        SalesOrderID,  
        NULL,  
        NULL,  
        SalesPersonID,    
        NULL,           
        NULL,           
        NULL,  
        NULL           
FROM   Sales.SalesOrderHeader  
WHERE     SalesOrderID=43659 or SalesOrderID=43661  
UNION ALL  
SELECT 3 as Tag,  
       1 as Parent,  
        SOD.SalesOrderID,  
        NULL,  
        NULL,  
        SalesPersonID,  
        SOH.SalesOrderID,  
        LineTotal,  
        ProductID,  
        OrderQty     
FROM    Sales.SalesOrderHeader SOH,Sales.SalesOrderDetail SOD  
WHERE   SOH.SalesOrderID = SOD.SalesOrderID  
AND     (SOH.SalesOrderID=43659 or SOH.SalesOrderID=43661)  
ORDER BY [OrderHeader!1!SalesOrderID], [SalesPerson!2!SalesPersonID],  
         [OrderDetail!3!SalesOrderID],[OrderDetail!3!LineTotal]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="77ecc-109">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="77ecc-109">This is the partial result:</span></span>  
  
 `<OrderHeader SalesOrderID="43659" OrderDate="2005-07-01T00:00:00" CustomerID="676">`  
  
 `<SalesPerson SalesPersonID="279" />`  
  
 `<OrderDetail SalesOrderID="43659" LineTotal="10.373000" ProductID="712" OrderQty="2" />`  
  
 `<OrderDetail SalesOrderID="43659" LineTotal="28.840400" ProductID="716" OrderQty="1" />`  
  
 `<OrderDetail SalesOrderID="43659" LineTotal="34.200000" ProductID="709" OrderQty="6" />`  
  
 `...`  
  
 `</OrderHeader>`  
  
 `<OrderHeader SalesOrderID="43661" OrderDate="2005-07-01T00:00:00" CustomerID="442">`  
  
 `<SalesPerson SalesPersonID="282" />`  
  
 `<OrderDetail SalesOrderID="43661" LineTotal="20.746000" ProductID="712" OrderQty="4" />`  
  
 `<OrderDetail SalesOrderID="43661" LineTotal="40.373000" ProductID="711" OrderQty="2" />`  
  
 `...`  
  
 `</OrderHeader>`  
  
## <a name="see-also"></a><span data-ttu-id="77ecc-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77ecc-110">See Also</span></span>  
 [<span data-ttu-id="77ecc-111">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="77ecc-111">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
