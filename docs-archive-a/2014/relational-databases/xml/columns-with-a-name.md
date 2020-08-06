---
title: Colonne provviste di un nome | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: c994e089-4cfc-4e9b-b7fc-e74f6014b51a
author: rothja
ms.author: jroth
ms.openlocfilehash: 32cfe617b80ed216374249961b85eae401011a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712848"
---
# <a name="columns-with-a-name"></a><span data-ttu-id="0326e-102">Colonne provviste di un nome</span><span class="sxs-lookup"><span data-stu-id="0326e-102">Columns with a Name</span></span>
  <span data-ttu-id="0326e-103">Di seguito vengono illustrate le condizioni specifiche in cui viene eseguito il mapping tra le colonne del set di righe provviste di nome e il codice XML risultante, con distinzione tra maiuscole e minuscole:</span><span class="sxs-lookup"><span data-stu-id="0326e-103">The following are the specific conditions in which rowset columns with a name are mapped, case-sensitive, to the resulting XML:</span></span>  
  
-   <span data-ttu-id="0326e-104">Il nome di colonna inizia con un simbolo di chiocciola (\@).</span><span class="sxs-lookup"><span data-stu-id="0326e-104">The column name starts with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="0326e-105">Il nome di colonna non inizia con un simbolo di chiocciola (\@).</span><span class="sxs-lookup"><span data-stu-id="0326e-105">The column name does not start with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="0326e-106">Il nome di colonna non inizia con un simbolo di chiocciola (\@) e contiene una barra (/).</span><span class="sxs-lookup"><span data-stu-id="0326e-106">The column name does not start with an at sign\@ and contains a slash mark (/).</span></span>  
  
-   <span data-ttu-id="0326e-107">Più colonne condividono lo stesso prefisso.</span><span class="sxs-lookup"><span data-stu-id="0326e-107">Several columns share the same prefix.</span></span>  
  
-   <span data-ttu-id="0326e-108">Una colonna ha un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="0326e-108">One column has a different name.</span></span>  
  
## <a name="column-name-starts-with-an-at-sign-"></a><span data-ttu-id="0326e-109">Il nome di colonna inizia con un simbolo di chiocciola (\@)</span><span class="sxs-lookup"><span data-stu-id="0326e-109">Column Name Starts with an At Sign (\@)</span></span>  
 <span data-ttu-id="0326e-110">Se il nome della colonna inizia con un simbolo di chiocciola ( \@ ) e non contiene una barra (/), viene creato un attributo dell' `row` elemento <> con il valore di colonna corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0326e-110">If the column name starts with an at sign (\@) and does not contain a slash mark (/), an attribute of the <`row`> element that has the corresponding column value is created.</span></span> <span data-ttu-id="0326e-111">Ad esempio, la query seguente restituisce un set di righe a due colonne (\@PmId, Name).</span><span class="sxs-lookup"><span data-stu-id="0326e-111">For example, the following query returns a two-column (\@PmId, Name) rowset.</span></span> <span data-ttu-id="0326e-112">Nel codice XML risultante, un attributo **PmId** viene aggiunto all'elemento <`row`> corrispondente e gli viene assegnato un valore di ProductModelID.</span><span class="sxs-lookup"><span data-stu-id="0326e-112">In the resulting XML, a **PmId** attribute is added to the corresponding <`row`> element and a value of ProductModelID is assigned to it.</span></span>  
  
```  
  
SELECT ProductModelID as "@PmId",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
  
```  
  
 <span data-ttu-id="0326e-113">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0326e-113">This is the result:</span></span>  
  
```  
<row PmId="7">  
  <Name>HL Touring Frame</Name>  
</row>  
```  
  
 <span data-ttu-id="0326e-114">Si noti che gli attributi devono precedere qualsiasi altro tipo di nodo presente nello stesso livello, ad esempio nodi di elemento e di testo.</span><span class="sxs-lookup"><span data-stu-id="0326e-114">Note that attributes must come before any other node types, such as element nodes and text nodes, in the same level.</span></span> <span data-ttu-id="0326e-115">La query seguente restituirà un errore:</span><span class="sxs-lookup"><span data-stu-id="0326e-115">The following query will return an error:</span></span>  
  
```  
SELECT Name,  
       ProductModelID as "@PmId"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign-"></a><span data-ttu-id="0326e-116">Il nome di colonna non inizia con un simbolo di chiocciola (\@)</span><span class="sxs-lookup"><span data-stu-id="0326e-116">Column Name Does Not Start with an At Sign (\@)</span></span>  
 <span data-ttu-id="0326e-117">Se il nome di colonna non inizia con un simbolo di chiocciola ( \@ ), non è uno dei test di nodo XPath e non contiene una barra (/), viene creato un elemento XML che è un sottoelemento dell'elemento riga <`row`> per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0326e-117">If the column name does not start with an at sign (\@), is not one of the XPath node tests, and does not contain a slash mark (/), an XML element that is a subelement of the row element, <`row`> by default, is created.</span></span>  
  
 <span data-ttu-id="0326e-118">La query seguente specifica il nome della colonna, il risultato.</span><span class="sxs-lookup"><span data-stu-id="0326e-118">The following query specifies the column name, the result.</span></span> <span data-ttu-id="0326e-119">Un elemento figlio <`result`> viene pertanto aggiunto all'elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-119">Therefore, a <`result`> element child is added to the <`row`> element.</span></span>  
  
```  
SELECT 2+2 as result  
for xml PATH  
```  
  
 <span data-ttu-id="0326e-120">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0326e-120">This is the result:</span></span>  
  
```  
<row>  
  <result>4</result>  
</row>  
```  
  
 <span data-ttu-id="0326e-121">La query seguente specifica il nome della colonna, ManuWorkCenterInformation, per il codice XML restituito dall'espressione XQuery specificata sulla colonna Instructions di tipo **xml**.</span><span class="sxs-lookup"><span data-stu-id="0326e-121">The following query specifies the column name, ManuWorkCenterInformation, for the XML returned by the XQuery specified against Instructions column of **xml** type.</span></span> <span data-ttu-id="0326e-122">Un elemento <`ManuWorkCenterInformation`> viene pertanto aggiunto come figlio dell'elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-122">Therefore, a <`ManuWorkCenterInformation`> element is added as a child of the <`row`> element.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') as ManuWorkCenterInformation  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
 <span data-ttu-id="0326e-123">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0326e-123">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>7</ProductModelID>  
  <Name>HL Touring Frame</Name>  
  <ManuWorkCenterInformation>  
    <MI:Location ...LocationID="10" ...></MI:Location>  
    <MI:Location ...LocationID="20" ...></MI:Location>  
     ...  
  </ManuWorkCenterInformation>  
</row>  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign--and-contains-a-slash-mark-"></a><span data-ttu-id="0326e-124">Il nome di colonna non inizia con un simbolo di chiocciola (\@) e contiene una barra (/)</span><span class="sxs-lookup"><span data-stu-id="0326e-124">Column Name Does Not Start with an At Sign (\@) and Contains a Slash Mark (/)</span></span>  
 <span data-ttu-id="0326e-125">Se il nome di colonna non inizia con un simbolo di chiocciola (\@), ma contiene una barra (/), il nome della colonna indica una gerarchia XML.</span><span class="sxs-lookup"><span data-stu-id="0326e-125">If the column name does not start with an at sign (\@), but contains a slash mark (/), the column name indicates an XML hierarchy.</span></span> <span data-ttu-id="0326e-126">Ad esempio, se il nome della colonna è "Name1/Name2/Name3.../Name***n*** ", ogni Name***i*** rappresenta un nome di elemento nidificato nell'elemento di riga corrente (per i=1) o che si trova sotto l'elemento il cui nome è Name***i-1***.</span><span class="sxs-lookup"><span data-stu-id="0326e-126">For example, if the column name is "Name1/Name2/Name3.../Name***n*** ", each Name***i*** represents an element name that is nested in the current row element (for i=1) or that is under the element that has the name Name***i-1***.</span></span> <span data-ttu-id="0326e-127">Se Name***n*** inizia con il simbolo '\@', viene mappato a un attributo dell'elemento Name***n-1***.</span><span class="sxs-lookup"><span data-stu-id="0326e-127">If Name***n*** starts with '\@', it is mapped to an attribute of Name***n-1*** element.</span></span>  
  
 <span data-ttu-id="0326e-128">Ad esempio, la query seguente restituisce l'ID e il nome di un dipendente rappresentati come un elemento complesso EmpName che contiene nome, secondo nome e cognome.</span><span class="sxs-lookup"><span data-stu-id="0326e-128">For example, the following query returns an employee ID and name that are represented as a complex element EmpName that contains a First, Middle, and Last name.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="0326e-129">I nomi di colonna vengono usati come un percorso nella creazione del codice XML in modalità PATH.</span><span class="sxs-lookup"><span data-stu-id="0326e-129">The column names are used as a path in constructing XML in the PATH mode.</span></span> <span data-ttu-id="0326e-130">Il nome della colonna che contiene i valori ID dipendente inizia con ' \@ '. Viene pertanto aggiunto un attributo **EmpID**all' `row` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="0326e-130">The column name that contains employee ID values, starts with '\@'.Therefore, an attribute, **EmpID**, is added to the <`row`> element.</span></span> <span data-ttu-id="0326e-131">I nomi di tutte le altre colonne contengono una barra ("/"), che indica la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="0326e-131">All other columns include a slash mark ('/') in the column name that indicates hierarchy.</span></span> <span data-ttu-id="0326e-132">Il codice XML risultante avrà l'elemento figlio <`EmpName`> sotto l'elemento <`row`> e l'elemento figlio <`EmpName`> avrà gli elementi figlio <`First`>, <`Middle`> e <`Last`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-132">The resulting XML will have the <`EmpName`> child under the <`row`> element, and the <`EmpName`> child will have <`First`>, <`Middle`> and <`Last`> element children.</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="0326e-133">Il valore del secondo nome del dipendente è Null e, per impostazione predefinita, il valore Null corrisponde all'assenza dell'elemento o attributo.</span><span class="sxs-lookup"><span data-stu-id="0326e-133">The employee middle name is null and, by default, the null value maps to the absence of the element or attribute.</span></span> <span data-ttu-id="0326e-134">Se si desidera la generazione di elementi per i valori NULL, è possibile specificare la direttiva ELEMENTS con XSINIL, come illustrato in questa query.</span><span class="sxs-lookup"><span data-stu-id="0326e-134">If you want elements generated for the NULL values, you can specify the ELEMENTS directive with XSINIL as shown in this query.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="0326e-135">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0326e-135">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
      EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="0326e-136">Per impostazione predefinita, la modalità PATH genera XML incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="0326e-136">By default, the PATH mode generates element-centric XML.</span></span> <span data-ttu-id="0326e-137">Specificare la direttiva ELEMENTS in una query in modalità PATH pertanto non produce effetti.</span><span class="sxs-lookup"><span data-stu-id="0326e-137">Therefore, specifying the ELEMENTS directive in a PATH mode query has no effect.</span></span> <span data-ttu-id="0326e-138">Come illustrato nell'esempio precedente tuttavia, la direttiva ELEMENTS risulta utile con XSINIL per la generazione di elementi per i valori Null.</span><span class="sxs-lookup"><span data-stu-id="0326e-138">However, as shown in the previous example, the ELEMENTS directive is useful with XSINIL to generate elements for null values.</span></span>  
  
 <span data-ttu-id="0326e-139">Oltre all'ID e al nome, la query seguente recupera l'indirizzo di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="0326e-139">Besides the ID and name, the following query retrieves an employee address.</span></span> <span data-ttu-id="0326e-140">Come per il percorso nei nomi di colonna per le colonne degli indirizzi, un elemento figlio <`Address`> viene aggiunto all'elemento <`row`> e i dettagli relativi agli indirizzi vengono aggiunti come elementi figlio dell'elemento <`Address`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-140">As per the path in the column names for address columns, an <`Address`> element child is added to the <`row`> element and the address details are added as element children of the <`Address`> element.</span></span>  
  
```  
SELECT EmployeeID   "@EmpID",   
       FirstName    "EmpName/First",   
       MiddleName   "EmpName/Middle",   
       LastName     "EmpName/Last",  
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City         "Address/City"  
FROM   HumanResources.Employee E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="0326e-141">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0326e-141">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
</row>  
```  
  
## <a name="several-columns-share-the-same-path-prefix"></a><span data-ttu-id="0326e-142">Più colonne condividono lo stesso prefisso di percorso</span><span class="sxs-lookup"><span data-stu-id="0326e-142">Several Columns Share the Same Path Prefix</span></span>  
 <span data-ttu-id="0326e-143">Se più colonne successive condividono lo stesso prefisso di percorso, vengono raggruppate sotto lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="0326e-143">If several subsequent columns share the same path prefix, they are grouped together under the same name.</span></span> <span data-ttu-id="0326e-144">Se vengono utilizzati prefissi degli spazi dei nomi diversi, anche se associati allo stesso spazio dei nomi, un percorso viene considerato diverso.</span><span class="sxs-lookup"><span data-stu-id="0326e-144">If different namespace prefixes are being used even if they are bound to the same namespace, a path is considered different.</span></span> <span data-ttu-id="0326e-145">Nella query precedente, le colonne FirstName, MiddleName e LastName condividono lo stesso prefisso EmpName. Vengono pertanto aggiunte come elementi figlio dell'elemento <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-145">In the previous query, the FirstName, MiddleName, and LastName columns share the same EmpName prefix.Therefore, they are added as children of the <`EmpName`> element.</span></span> <span data-ttu-id="0326e-146">Ciò si verifica anche nell'esempio precedente, nella fase di creazione dell'elemento <`Address`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-146">This is also the case when you were creating the <`Address`> element in the previous example.</span></span>  
  
## <a name="one-column-has-a-different-name"></a><span data-ttu-id="0326e-147">Una colonna ha un nome diverso</span><span class="sxs-lookup"><span data-stu-id="0326e-147">One Column Has a Different Name</span></span>  
 <span data-ttu-id="0326e-148">Se è presente una colonna con un nome diverso, interromperà il raggruppamento, come illustrato nella query modificata seguente.</span><span class="sxs-lookup"><span data-stu-id="0326e-148">If a column with a different name appears in between, it will break the grouping, as shown in the following modified query.</span></span> <span data-ttu-id="0326e-149">La query interrompe il raggruppamento di FirstName, MiddleName e LastName, come specificato nella query precedente, aggiungendo colonne di indirizzi fra le colonne FirstName e MiddleName.</span><span class="sxs-lookup"><span data-stu-id="0326e-149">The query breaks the grouping of FirstName, MiddleName, and LastName, as specified in the previous query, by adding address columns in between the FirstName and MiddleName columns.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName "EmpName/First",   
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City "Address/City",  
       MiddleName "EmpName/Middle",   
       LastName "EmpName/Last"  
FROM   HumanResources.EmployeeAddress E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="0326e-150">Di conseguenza, la query crea due elementi <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-150">As a result, the query creates two <`EmpName`> elements.</span></span> <span data-ttu-id="0326e-151">Il primo elemento <`EmpName`> ha l'elemento figlio <`FirstName`> e il secondo elemento <`EmpName`> ha gli elementi figlio <`MiddleName`> e <`LastName`>.</span><span class="sxs-lookup"><span data-stu-id="0326e-151">The first <`EmpName`> element has the <`FirstName`> element child and the second <`EmpName`> element has the <`MiddleName`> and <`LastName`> element children.</span></span>  
  
 <span data-ttu-id="0326e-152">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0326e-152">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
  <EmpName>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0326e-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0326e-153">See Also</span></span>  
 [<span data-ttu-id="0326e-154">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="0326e-154">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
