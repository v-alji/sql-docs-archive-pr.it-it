---
title: 'Esempio: Specifica della direttiva XMLTEXT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XMLTEXT directive
ms.assetid: e78008ec-51e8-4fd1-b86f-1058a781de17
author: rothja
ms.author: jroth
ms.openlocfilehash: d14299ad3e989c6600434b857a650fbbddd7a590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636597"
---
# <a name="example-specifying-the-xmltext-directive"></a><span data-ttu-id="2b1ba-102">Esempio: Specifica della direttiva XMLTEXT</span><span class="sxs-lookup"><span data-stu-id="2b1ba-102">Example: Specifying the XMLTEXT Directive</span></span>
  <span data-ttu-id="2b1ba-103">Nell'esempio seguente viene illustrata la gestione dei dati nella colonna di overflow utilizzando la direttiva `XMLTEXT` in un'istruzione `SELECT` in modalità EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-103">This example illustrates how data in the overflow column is addressed by using the `XMLTEXT` directive in a `SELECT` statement using EXPLICIT mode.</span></span>  
  
 <span data-ttu-id="2b1ba-104">Si consideri la tabella `Person` .</span><span class="sxs-lookup"><span data-stu-id="2b1ba-104">Consider the `Person` table.</span></span> <span data-ttu-id="2b1ba-105">La tabella contiene una colonna `Overflow` in cui viene archiviata la parte non utilizzata del documento XML.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-105">This table has an `Overflow` column that stores the unconsumed part of the XML document.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE TABLE Person(PersonID varchar(5), PersonName varchar(20), Overflow nvarchar(200));  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
   ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P">content</SomeTag>');  
```  
  
 <span data-ttu-id="2b1ba-106">Questa query recupera colonne dalla tabella `Person` .</span><span class="sxs-lookup"><span data-stu-id="2b1ba-106">This query retrieves columns from the `Person` table.</span></span> <span data-ttu-id="2b1ba-107">Per la colonna `Overflow` non è specificato *AttributeName* , ma la *direttiva* è impostata su `XMLTEXT` nell'ambito della specifica del nome della colonna della tabella universale.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-107">For the `Overflow` column, *AttributeName* is not specified, but *directive* is set to `XMLTEXT` as part of providing a universal table column name.</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEST] -- No AttributeName; XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="2b1ba-108">Nel documento XML risultante:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-108">In the resulting XML document:</span></span>  
  
-   <span data-ttu-id="2b1ba-109">Poiché *AttributeName* non è specificato per la colonna `Overflow` ed è specificata la direttiva `xmltext`, gli attributi nell'elemento <`overflow`> vengono accodati all'elenco attributi dell'elemento <`Parent`> che li racchiude.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-109">Because *AttributeName* is not specified for the `Overflow` column and the `xmltext` directive is specified, the attributes in the <`overflow`> element are appended to the attribute list of the enclosing <`Parent`> element.</span></span>  
  
-   <span data-ttu-id="2b1ba-110">Poiché l'attributo `PersonID` nell'elemento <`xmltext`> è in conflitto con l'attributo `PersonID` recuperato allo stesso livello dell'elemento, l'attributo dell'elemento <`xmltext`> viene ignorato, anche se `PersonID` è NULL.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-110">Because the `PersonID`attribute in the <`xmltext`> element conflicts with the `PersonID` attribute retrieved on the same element level, the attribute in the <`xmltext`> element is ignored, even if `PersonID` is NULL.</span></span> <span data-ttu-id="2b1ba-111">In linea generale, nell'overflow un attributo prevarrà sull'attributo con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-111">Generally, an attribute overrides an attribute of the same name in the overflow.</span></span>  
  
 <span data-ttu-id="2b1ba-112">Risultato:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-112">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">content</Parent>`  
  
 <span data-ttu-id="2b1ba-113">Se i dati di overflow includono sottoelementi e si specifica la stessa query, i sottoelementi nella colonna `Overflow` vengono aggiunti come sottoelementi dell'elemento <`Parent`> che li racchiude.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-113">If the overflow data has subelements and the same query is specified, the subelements in the `Overflow` column are added as the subelements of the enclosing <`Parent`> element.</span></span>  
  
 <span data-ttu-id="2b1ba-114">Modificare, ad esempio, i dati della tabella `Person` in modo che la colonna `Overflow` includa sottoelementi.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-114">For example, change the data in the `Person` table so that the `Overflow` column now has subelements.</span></span>  
  
```  
USE tempdb;  
GO  
TRUNCATE TABLE Person;  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
    ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P"><name>PersonName</name></SomeTag>');  
```  
  
 <span data-ttu-id="2b1ba-115">Se si esegue la stessa query, i sottoelementi dell'elemento <`xmltext`> vengono aggiunti come sottoelementi dell'elemento <`Parent`> che li racchiude:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-115">If the same query is executed, the subelements in the <`xmltext`> element are added as subelements of the enclosing <`Parent`> element:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEXT] -- no AttributeName, XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="2b1ba-116">Risultato:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-116">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `</Parent>`  
  
 <span data-ttu-id="2b1ba-117">Se si specifica*AttributeName* con la direttiva `xmltext`, gli attributi dell'elemento <`overflow`> vengono aggiunti come attributi dei sottoelementi dell'elemento <`Parent`> che li racchiude.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-117">If *AttributeName* is specified with the `xmltext` directive, the attributes of the <`overflow`> element are added as attributes of the subelements of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="2b1ba-118">Il nome specificato per *attributeName* diventa il nome del sottoelemento.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-118">The name specified for *AttributeName* becomes the name of the subelement.</span></span>  
  
 <span data-ttu-id="2b1ba-119">In questa query, *attributeName*, <`overflow`>, viene specificato insieme alla `xmltext` direttiva:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-119">In this query, *AttributeName*, <`overflow`>, is specified together with the `xmltext` directive:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!overflow!XMLTEXT] -- Overflow is AttributeName  
                      -- XMLTEXT is a directive  
FROM Person  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="2b1ba-120">Risultato:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-120">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe">`  
  
 `<overflow attr1="data">content</overflow>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe">`  
  
 `<overflow attr2="data" />`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe">`  
  
 `<overflow attr3="data" PersonID="P">`  
  
 `<name>PersonName</name>`  
  
 `</overflow>`  
  
 `</Parent>`  
  
 <span data-ttu-id="2b1ba-121">In questo elemento di query la *direttiva* viene specificata per l'attributo `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="2b1ba-121">In this query element, *directive* is specified for `PersonName` attribute.</span></span> <span data-ttu-id="2b1ba-122">`PersonName` verrà pertanto aggiunto come sottoelemento dell'elemento <`Parent`> che lo racchiude.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-122">This results in `PersonName` being added as a subelement of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="2b1ba-123">Gli attributi dell'elemento <`xmltext`> vengono aggiunti all'elemento <`Parent`> che li racchiude.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-123">The attributes of the <`xmltext`> are still appended to the enclosing <`Parent`> element.</span></span> <span data-ttu-id="2b1ba-124">Il contenuto dell'elemento <`overflow`> e i sottoelementi vengono anteposti agli altri sottoelementi degli elementi <`Parent`> che li racchiudono.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-124">The contents of the <`overflow`> element, subelements, are prepended to the other subelements of the enclosing <`Parent`> elements.</span></span>  
  
```  
SELECT 1      AS Tag, NULL as parent,  
       PersonID   AS [Parent!1!PersonID],  
       PersonName AS [Parent!1!PersonName!element], -- element directive  
       Overflow   AS [Parent!1!!XMLTEXT]  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="2b1ba-125">Risultato:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-125">This is the result:</span></span>  
  
 `<Parent PersonID="P1" attr1="data">content<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" attr2="data">`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 <span data-ttu-id="2b1ba-126">Se i dati della colonna `XMLTEXT` includono attributi per l'elemento radice, tali attributi non compaiono nello schema dei dati XML e il parser MSXML non convalida il frammento di documento XML risultante.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-126">If the `XMLTEXT` column data contains attributes on the root element, these attributes are not shown in the XML data schema and the MSXML parser does not validate the resulting XML document fragment.</span></span> <span data-ttu-id="2b1ba-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-127">For example:</span></span>  
  
```  
SELECT 1 AS Tag,  
       0 ASParent,  
       N'<overflow a="1"/>' AS 'overflow!1!!xmltext'  
FOR XML EXPLICIT, xmldata;  
```  
  
 <span data-ttu-id="2b1ba-128">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="2b1ba-128">This is the result.</span></span> <span data-ttu-id="2b1ba-129">L'attributo di overflow `a` manca dallo schema restituito:</span><span class="sxs-lookup"><span data-stu-id="2b1ba-129">Note that in the returned schema, the overflow attribute `a` is missing from the schema:</span></span>  
  
 `<Schema name="Schema2"`  
  
 `xmlns="urn:schemas-microsoft-com:xml-data"`  
  
 `xmlns:dt="urn:schemas-microsoft-com:datatypes">`  
  
 `<ElementType name="overflow" content="mixed" model="open">`  
  
 `</ElementType>`  
  
 `</Schema>`  
  
 `<overflow xmlns="x-schema:#Schema2" a="1">`  
  
 `</overflow>`  
  
## <a name="see-also"></a><span data-ttu-id="2b1ba-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b1ba-130">See Also</span></span>  
 [<span data-ttu-id="2b1ba-131">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="2b1ba-131">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
