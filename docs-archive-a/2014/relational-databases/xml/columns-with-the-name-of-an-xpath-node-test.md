---
title: Colonne con il nome di un test di nodo XPath | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6555815d97308bed6e70d9fedb9858fc3abe7685
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713940"
---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a><span data-ttu-id="9bb4f-102">Colonne con il nome di un test di nodo XPath</span><span class="sxs-lookup"><span data-stu-id="9bb4f-102">Columns with the Name of an XPath Node Test</span></span>
  <span data-ttu-id="9bb4f-103">Se il nome della colonna è uno dei test di nodo XPath, il mapping del contenuto viene eseguito come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-103">If the column name is one of the XPath node tests, the content is mapped as shown in the following table.</span></span> <span data-ttu-id="9bb4f-104">Quando il nome della colonna è un test di nodo XPath, il mapping viene eseguito tra il contenuto e il nodo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-104">When the column name is an XPath node test, the content is mapped to the corresponding node.</span></span> <span data-ttu-id="9bb4f-105">Se il tipo SQL della colonna è `xml`, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-105">If the SQL type of the column is `xml`, an error is returned.</span></span>  
  
|<span data-ttu-id="9bb4f-106">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9bb4f-106">Column Name</span></span>|<span data-ttu-id="9bb4f-107">Comportamento</span><span class="sxs-lookup"><span data-stu-id="9bb4f-107">Behavior</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="9bb4f-108">text()</span><span class="sxs-lookup"><span data-stu-id="9bb4f-108">text()</span></span>|<span data-ttu-id="9bb4f-109">Per una colonna con nome text(), il valore stringa contenuto nella colonna viene aggiunto come nodo di testo.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-109">For a column with the name of text(), the string value in that column is added as a text node.</span></span>|  
|<span data-ttu-id="9bb4f-110">comment()</span><span class="sxs-lookup"><span data-stu-id="9bb4f-110">comment()</span></span>|<span data-ttu-id="9bb4f-111">Per una colonna con nome comment(), il valore stringa contenuto nella colonna viene aggiunto come commento XML.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-111">For a column with the name of comment(), the string value in that column is added as an XML comment.</span></span>|  
|<span data-ttu-id="9bb4f-112">node()</span><span class="sxs-lookup"><span data-stu-id="9bb4f-112">node()</span></span>|<span data-ttu-id="9bb4f-113">Per una colonna con nome node(), il risultato è lo stesso di quando il nome della colonna è un carattere jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="9bb4f-113">For a column with the name of node(), the result is the same as it is when the column name is a wildcard character (\*).</span></span>|  
|<span data-ttu-id="9bb4f-114">processing-instruction(name)</span><span class="sxs-lookup"><span data-stu-id="9bb4f-114">processing-instruction(name)</span></span>|<span data-ttu-id="9bb4f-115">Per una colonna il cui nome corrisponde a quello di un'istruzione di elaborazione, il valore stringa contenuto nella colonna viene aggiunto come valore PI per il nome di destinazione dell'istruzione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-115">For a column with the name of a processing instruction, the string value in that column is added as the PI value for the processing instruction target name.</span></span>|  
  
 <span data-ttu-id="9bb4f-116">Nella query seguente viene illustrato l'utilizzo dei test di nodo come nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-116">The following query shows the use of the node tests as column names.</span></span> <span data-ttu-id="9bb4f-117">I nodi di testo e i commenti vengono aggiunti nel codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="9bb4f-117">It adds text nodes and comments in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="9bb4f-118">Risultato:</span><span class="sxs-lookup"><span data-stu-id="9bb4f-118">This is the result:</span></span>  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>S??nchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="9bb4f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bb4f-119">See Also</span></span>  
 [<span data-ttu-id="9bb4f-120">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="9bb4f-120">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
