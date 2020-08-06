---
title: 'Esempio: Specifica della direttiva ELEMENT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
ms.assetid: 80dd5d1f-fa90-4f97-a186-8fa3f460a7f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a03d1049fa9df23eff759634bcd74f88f842a8e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711783"
---
# <a name="example-specifying-the-element-directive"></a><span data-ttu-id="29961-102">Esempio: Specifica della direttiva ELEMENT</span><span class="sxs-lookup"><span data-stu-id="29961-102">Example: Specifying the ELEMENT Directive</span></span>
  <span data-ttu-id="29961-103">In questo modo vengono recuperate le informazioni sul personale e viene generato un valore XML incentrato sugli attributi, come mostrato negli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="29961-103">This retrieves employee information and generates element-centric XML as shown in the following:</span></span>  
  
```  
<Employee EmpID=...>  
  <Name>  
    <FName>...</FName>  
    <LName>...</LName>  
  </Name>  
</Employee>  
```  
  
 <span data-ttu-id="29961-104">La query viene mantenuta, ma si aggiunge la direttiva `ELEMENT` nei nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="29961-104">The query remains the same, except you add the `ELEMENT` directive in the column names.</span></span> <span data-ttu-id="29961-105"><`FName`> e <`LName`> vengono pertanto aggiunti come elementi figlio dell'elemento <`Name`> invece che come attributi.</span><span class="sxs-lookup"><span data-stu-id="29961-105">Therefore, instead of attributes, the <`FName`> and <`LName`> element children are added to the <`Name`> element.</span></span> <span data-ttu-id="29961-106">Poiché nella colonna `Employee!1!EmpID` non è specificata la direttiva `ELEMENT`, `EmpID` viene aggiunto come attributo dell'elemento <`Employee`>.</span><span class="sxs-lookup"><span data-stu-id="29961-106">Because the `Employee!1!EmpID` column does not specify the `ELEMENT` directive, `EmpID` is added as the attribute of the <`Employee`> element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName!ELEMENT],  
       NULL       as [Name!2!LName!ELEMENT]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName!ELEMENT]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="29961-107">Di seguito è riportato il risultato parziale.</span><span class="sxs-lookup"><span data-stu-id="29961-107">This is the partial result.</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name>`  
  
 `<FName>Ken</FName>`  
  
 `<LName>S??nchez</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name>`  
  
 `<FName>Terri</FName>`  
  
 `<LName>Duffy</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `...`  
  
## <a name="see-also"></a><span data-ttu-id="29961-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29961-108">See Also</span></span>  
 [<span data-ttu-id="29961-109">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="29961-109">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
