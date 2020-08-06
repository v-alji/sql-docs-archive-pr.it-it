---
title: 'Esempio: specifica della direttiva ELEMENT e della codifica di entità | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
- entity encoding [XML]
ms.assetid: 50cda5c1-7293-4080-93b3-872e3b8d484e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ba4e419d31aa7c02cc2dc8f19a3350c233f042b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711792"
---
# <a name="example-specifying-the-element-directive-and-entity-encoding"></a><span data-ttu-id="d22fc-102">Esempio: Specifica della direttiva ELEMENT e della codifica di entità</span><span class="sxs-lookup"><span data-stu-id="d22fc-102">Example: Specifying the ELEMENT Directive and Entity Encoding</span></span>
  <span data-ttu-id="d22fc-103">In questo esempio viene illustrata la differenza fra le direttive **ELEMENT** e **XML** .</span><span class="sxs-lookup"><span data-stu-id="d22fc-103">This example illustrates the difference between the **ELEMENT** and **XML** directives.</span></span> <span data-ttu-id="d22fc-104">La direttiva **ELEMENT** sostituisce i dati con entità, mentre la direttiva **XML** non esegue questa operazione.</span><span class="sxs-lookup"><span data-stu-id="d22fc-104">The **ELEMENT** directive entitizes the data, but the **XML** directive does not.</span></span> <span data-ttu-id="d22fc-105">Nella query, all'elemento \<Summary> viene assegnato codice XML, `<Summary>This is summary description</Summary>`.</span><span class="sxs-lookup"><span data-stu-id="d22fc-105">The \<Summary> element is assigned XML, `<Summary>This is summary description</Summary>`, in the query.</span></span>  
  
 <span data-ttu-id="d22fc-106">Considerare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="d22fc-106">Consider this query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription!ELEMENT]  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        NULL,  
       '<Summary>This is summary description</Summary>'  
FROM   Production.ProductModel  
WHERE  ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="d22fc-107">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="d22fc-107">This is the result.</span></span> <span data-ttu-id="d22fc-108">Nel risultato la descrizione di riepilogo viene sostituita con entità.</span><span class="sxs-lookup"><span data-stu-id="d22fc-108">The summary description is entitized in the result.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription><Summary>This is summary description</Summary></SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="d22fc-109">Se nel nome della colonna **si specifica la direttiva** XML `Summary!2!SummaryDescription!XML`invece della direttiva **ELEMENT** , si otterrà la descrizione di riepilogo senza sostituzione con entità.</span><span class="sxs-lookup"><span data-stu-id="d22fc-109">Now, if you specify the **XML** directive in the column name, `Summary!2!SummaryDescription!XML`, instead of the **ELEMENT** directive, you will receive the summary description without entitization.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <Summary>This is summary description</Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="d22fc-110">Invece di assegnare un valore XML statico, la query seguente usa il metodo **query()** del tipo **xml** per recuperare la descrizione di riepilogo del modello di prodotto dalla colonna CatalogDescription di tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="d22fc-110">Instead of assigning a static XML value, the following query uses the **query()** method of the **xml** type to retrieve the product model summary description from the CatalogDescription column of **xml** type.</span></span> <span data-ttu-id="d22fc-111">Poiché è noto che il risultato sarà di tipo **xml** , non viene applicata la sostituzione con entità.</span><span class="sxs-lookup"><span data-stu-id="d22fc-111">Because the result is known to be of **xml** type, no entitization is applied.</span></span>  
  
```  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
       (SELECT CatalogDescription.query('  
            declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
          /pd:ProductDescription/pd:Summary'))  
FROM     Production.ProductModel  
WHERE    CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],Tag  
FOR XML EXPLICIT  
```  
  
## <a name="see-also"></a><span data-ttu-id="d22fc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d22fc-112">See Also</span></span>  
 [<span data-ttu-id="d22fc-113">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="d22fc-113">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
