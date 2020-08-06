---
title: 'Esempio: esecuzione di query sulle colonne di tipo XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, querying XML example
ms.assetid: d9f3710d-7a2e-4abe-9c02-3e3c0df4d620
author: rothja
ms.author: jroth
ms.openlocfilehash: 0eedfa5a5a265f3715a76a6ca80d489bbec199bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623934"
---
# <a name="example-querying-xmltype-columns"></a><span data-ttu-id="b5b73-102">Esempio: esecuzione di query sulle colonne di tipo XML</span><span class="sxs-lookup"><span data-stu-id="b5b73-102">Example: Querying XMLType Columns</span></span>
  <span data-ttu-id="b5b73-103">Nella query seguente sono incluse colonne di tipo `xml`</span><span class="sxs-lookup"><span data-stu-id="b5b73-103">The following query includes columns of `xml` type.</span></span> <span data-ttu-id="b5b73-104">e vengono recuperati l'ID del modello del prodotto, il nome e le fasi di produzione nel primo centro di lavorazione dalla colonna `Instructions` di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="b5b73-104">The query retrieves product model ID, name, and manufacturing steps at the first location from the `Instructions` column of the `xml` type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5b73-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5b73-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
')   
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
GO  
```  
  
 <span data-ttu-id="b5b73-106">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="b5b73-106">The following is the result.</span></span> <span data-ttu-id="b5b73-107">Si noti che nella tabella sono archiviate le istruzioni di produzione relative unicamente ad alcuni modelli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="b5b73-107">Note that the table stores manufacturing instructions for only some product models.</span></span> <span data-ttu-id="b5b73-108">Nel risultato, le fasi di produzione vengono restituite come sottoelementi dell'elemento <`ProductModelData`>.</span><span class="sxs-lookup"><span data-stu-id="b5b73-108">The manufacturing steps are returned as subelements of the <`ProductModelData`> element in the result.</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
    <MI:step> ... </MI:step>  
    <MI:step> ... </MI:step>  
 </ProductModelData>  
```  
  
 <span data-ttu-id="b5b73-109">Se la query specifica un nome di colonna per il codice XML restituito dalla query XQuery, come illustrato nell'istruzione `SELECT` seguente, viene eseguito il wrapping delle fasi di produzione nell'elemento con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="b5b73-109">If the query specifies a column name for the XML returned by the XQuery, as specified in the following `SELECT` statement, the manufacturing steps are wrapped in the element that has the specified name.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
go  
```  
  
 <span data-ttu-id="b5b73-110">Risultato:</span><span class="sxs-lookup"><span data-stu-id="b5b73-110">This is the result:</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
  <ManuSteps>  
    <MI:step ... </MI:step>  
    <MI:step ... </MI:step>  
  </ManuSteps>  
</ProductModelData>  
```  
  
 <span data-ttu-id="b5b73-111">La query seguente specifica la direttiva `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="b5b73-111">The following query specifies the `ELEMENTS` directive.</span></span> <span data-ttu-id="b5b73-112">e pertanto il risultato restituito sarà incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="b5b73-112">Therefore, the result returned is element-centric.</span></span> <span data-ttu-id="b5b73-113">L'opzione `XSINIL` specificata insieme alla direttiva `ELEMENTS` restituisce gli elementi <`ManuSteps`> anche se la colonna corrispondente nel set di righe è NULL.</span><span class="sxs-lookup"><span data-stu-id="b5b73-113">The `XSINIL` option specified with the `ELEMENTS` directive returns the <`ManuSteps`> elements, even if the corresponding column in the rowset is NULL.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData'), root('MyRoot'), ELEMENTS XSINIL  
go  
```  
  
 <span data-ttu-id="b5b73-114">Risultato:</span><span class="sxs-lookup"><span data-stu-id="b5b73-114">This is the result:</span></span>  
  
```  
<MyRoot xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   ...  
  <ProductModelData>  
    <ProductModelID>6</ProductModelID>  
    <Name>HL Road Frame</Name>  
    <ManuSteps xsi:nil="true" />  
  </ProductModelData>  
  <ProductModelData>  
    <ProductModelID>7</ProductModelID>  
    <Name>HL Touring Frame</Name>  
    <ManuSteps>  
      <MI:step ... </MI:step>  
      <MI:step ...</MI:step>  
       ...  
    </ManuSteps>  
  </ProductModelData>  
</MyRoot>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5b73-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5b73-115">See Also</span></span>  
 [<span data-ttu-id="b5b73-116">Usare la modalità RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="b5b73-116">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
