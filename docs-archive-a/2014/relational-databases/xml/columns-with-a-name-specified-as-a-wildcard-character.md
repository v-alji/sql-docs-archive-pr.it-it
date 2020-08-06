---
title: Colonne con nome specificato come carattere jolly | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: d9551df1-5bb4-4c0b-880a-5bb049834884
author: rothja
ms.author: jroth
ms.openlocfilehash: 4b363baf8792628c2e17b1a695c19a6a338f4fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628542"
---
# <a name="columns-with-a-name-specified-as-a-wildcard-character"></a><span data-ttu-id="7911d-102">Colonne con nome specificato come carattere jolly</span><span class="sxs-lookup"><span data-stu-id="7911d-102">Columns with a Name Specified as a Wildcard Character</span></span>
  <span data-ttu-id="7911d-103">Se il nome di colonna specificato è un carattere jolly (\*), il contenuto della colonna viene inserito come se non fosse stato specificato alcun nome di colonna.</span><span class="sxs-lookup"><span data-stu-id="7911d-103">If the column name specified is a wildcard character (\*), the content of that column is inserted as if there is no column name specified.</span></span> <span data-ttu-id="7911d-104">Se la colonna non è di tipo `xml`, il relativo contenuto viene inserito come nodo di testo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7911d-104">If this column is a non-`xml` type column, the column content is inserted as a text node, as shown in the following example:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
       FirstName "*",   
       MiddleName "*",   
       LastName "*"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
    ON E.BusinessEntityID = P.BusinessEntityID  
WHERE E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="7911d-105">Risultato:</span><span class="sxs-lookup"><span data-stu-id="7911d-105">This is the result:</span></span>  
  
 `<row EmpID="1">KenJS??nchez</row>`  
  
 <span data-ttu-id="7911d-106">Se la colonna è di tipo `xml`, viene inserito l'albero XML corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7911d-106">If the column is of `xml` type, the corresponding XML tree is inserted.</span></span> <span data-ttu-id="7911d-107">Ad esempio, la query seguente specifica "\*" come nome della colonna che contiene il codice XML restituito dall'espressione XQuery eseguita sulla colonna Instructions.</span><span class="sxs-lookup"><span data-stu-id="7911d-107">For example, the following query specifies "\*" for the column name that contains the XML returned by the XQuery against the Instructions column.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
                /MI:root/MI:Location   
              ') as "*"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH;   
GO  
```  
  
 <span data-ttu-id="7911d-108">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="7911d-108">This is the result.</span></span> <span data-ttu-id="7911d-109">Il codice XML restituito dalla XQuery viene inserito senza un elemento di wrapping.</span><span class="sxs-lookup"><span data-stu-id="7911d-109">The XML returned by XQuery is inserted without a wrapping element.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location LocationID="10">...</MI:Location>`  
  
 `<MI:Location LocationID="20">...</MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="7911d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7911d-110">See Also</span></span>  
 [<span data-ttu-id="7911d-111">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="7911d-111">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
