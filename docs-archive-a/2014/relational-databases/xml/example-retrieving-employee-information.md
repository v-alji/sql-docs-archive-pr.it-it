---
title: 'Esempio: Recupero di informazioni sui dipendenti | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- EXPLICIT mode
ms.assetid: 63cd6569-2600-485b-92b4-1f6ba09db219
author: rothja
ms.author: jroth
ms.openlocfilehash: ae4578aedb7dbcc63388d5ef797e3a0bf5d8c306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629272"
---
# <a name="example-retrieving-employee-information"></a><span data-ttu-id="e62d9-102">Esempio: Recupero di informazioni sui dipendenti</span><span class="sxs-lookup"><span data-stu-id="e62d9-102">Example: Retrieving Employee Information</span></span>
  <span data-ttu-id="e62d9-103">In questo esempio vengono recuperati ID e nome di ogni dipendente.</span><span class="sxs-lookup"><span data-stu-id="e62d9-103">This example retrieves an employee ID and employee name for each employee.</span></span> <span data-ttu-id="e62d9-104">Nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] è possibile ottenere il valore employeeID dalla colonna BusinessEntityID della tabella Employee.</span><span class="sxs-lookup"><span data-stu-id="e62d9-104">In the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, the employeeID can be obtained from the BusinessEntityID column in the Employee table.</span></span> <span data-ttu-id="e62d9-105">I nomi dei dipendenti possono essere ottenuti dalla tabella Person.</span><span class="sxs-lookup"><span data-stu-id="e62d9-105">Employee names can be obtained from the Person table.</span></span> <span data-ttu-id="e62d9-106">La colonna BusinessEntityID può essere utilizzata per unire in join le tabelle.</span><span class="sxs-lookup"><span data-stu-id="e62d9-106">The BusinessEntityID column can be used to join the tables.</span></span>  
  
 <span data-ttu-id="e62d9-107">Si supponga di voler utilizzare la trasformazione FOR XML EXPLICIT per generare codice XML come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e62d9-107">Assume that you want FOR XML EXPLICIT transformation to generate XML as shown in the following:</span></span>  
  
```  
<Employee EmpID="1" >  
  <Name FName="Ken" LName="S??nchez" />  
</Employee>  
...  
```  
  
 <span data-ttu-id="e62d9-108">Poiché la gerarchia contiene due livelli, è necessario scrivere due query `SELECT` e applicare UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="e62d9-108">Because there are two levels in the hierarchy, you would write two `SELECT` queries and apply UNION ALL.</span></span> <span data-ttu-id="e62d9-109">Questa è la prima query che recupera i valori per l'elemento <`Employee`> e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="e62d9-109">This is the first query that retrieves values for the <`Employee`> element and its attributes.</span></span> <span data-ttu-id="e62d9-110">La query assegna `1` come valore di `Tag` per l'elemento <`Employee`> e NULL come `Parent`, poiché si tratta dell'elemento di livello principale.</span><span class="sxs-lookup"><span data-stu-id="e62d9-110">The query assigns `1` as `Tag` value for the <`Employee`> element and NULL as `Parent`, because it is the top-level element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID AS [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="e62d9-111">Di seguito è riportata la seconda query,</span><span class="sxs-lookup"><span data-stu-id="e62d9-111">This is the second query.</span></span> <span data-ttu-id="e62d9-112">che recupera i valori per l'elemento <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="e62d9-112">It retrieves values for the <`Name`> element.</span></span> <span data-ttu-id="e62d9-113">Assegna `2` come valore di `Tag` per l'elemento <`Name`> e `1` come valore di tag `Parent`, identificando <`Employee`> come elemento padre.</span><span class="sxs-lookup"><span data-stu-id="e62d9-113">It assigns `2` as `Tag` value for the <`Name`> element and `1` as `Parent` tag value identifying <`Employee`> as the parent.</span></span>  
  
```  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="e62d9-114">È necessario combinare queste query con `UNION AL`L, applicare `FOR XML EXPLICIT`e specificare la clausola obbligatoria `ORDER BY` .</span><span class="sxs-lookup"><span data-stu-id="e62d9-114">You combine these queries with `UNION AL`L, apply `FOR XML EXPLICIT`, and specify the required `ORDER BY` clause.</span></span> <span data-ttu-id="e62d9-115">Il set di righe deve essere ordinato prima per `BusinessEntityID` e quindi per nome, in modo che i valori NULL nel nome vengano visualizzati per primi.</span><span class="sxs-lookup"><span data-stu-id="e62d9-115">You must sort the rowset first by `BusinessEntityID` and then by name so that the NULL values in the name appear first.</span></span> <span data-ttu-id="e62d9-116">Eseguendo la query successiva senza la clausola FOR XML viene generata la tabella universale.</span><span class="sxs-lookup"><span data-stu-id="e62d9-116">By executing the following query without the FOR XML clause, you can see the universal table generated.</span></span>  
  
 <span data-ttu-id="e62d9-117">La query finale sarà pertanto:</span><span class="sxs-lookup"><span data-stu-id="e62d9-117">This is the final query:</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
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
ORDER BY [Employee!1!EmpID],[Name!2!FName]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="e62d9-118">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="e62d9-118">This is the partial result:</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name FName="Ken" LName="S??nchez" />`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name FName="Terri" LName="Duffy" />`  
  
 `</Employee>`  
  
 `...`  
  
 <span data-ttu-id="e62d9-119">La prima istruzione `SELECT` specifica i nomi per le colonne nel set di righe risultante.</span><span class="sxs-lookup"><span data-stu-id="e62d9-119">The first `SELECT` specifies names for columns in the resulting rowset.</span></span> <span data-ttu-id="e62d9-120">I nomi formano due gruppi di colonne.</span><span class="sxs-lookup"><span data-stu-id="e62d9-120">These names form two column groups.</span></span> <span data-ttu-id="e62d9-121">Il gruppo con valore di `Tag` pari a `1` nel nome della colonna identifica `Employee` come elemento ed `EmpID` come attributo.</span><span class="sxs-lookup"><span data-stu-id="e62d9-121">The group that has `Tag` value `1` in the column name identifies `Employee` as an element and `EmpID` as the attribute.</span></span> <span data-ttu-id="e62d9-122">L'altro gruppo di colonne contiene il valore di `Tag``2` nella colonna e identifica <`Name`> come elemento e `FName` e `LName` come attributi.</span><span class="sxs-lookup"><span data-stu-id="e62d9-122">The other column group has `Tag` value `2` in the column and identifies <`Name`> as the element and `FName` and `LName` as the attributes.</span></span>  
  
 <span data-ttu-id="e62d9-123">La tabella seguente mostra il set di righe parziale generato dalla query:</span><span class="sxs-lookup"><span data-stu-id="e62d9-123">The following table shows the partial rowset generated by the query:</span></span>  
  
 `Tag Parent  Employee!1!EmpID Name!2!FName Name!2!LName`  
  
 `--- ------  ---------------- ------------ ------------`  
  
 `1   NULL    1                NULL         NULL`  
  
 `2   1       1                Ken          S??nchez`  
  
 `1   NULL    2                NULL         NULL`  
  
 `2   1       2                Terri        Duffy`  
  
 `1   NULL    3                NULL         NULL`  
  
 `2   1       3                Roberto      Tamburello`  
  
 `...`  
  
 <span data-ttu-id="e62d9-124">Di seguito viene descritto il processo di elaborazione delle righe della tabella universale per la creazione dell'albero XML risultante:</span><span class="sxs-lookup"><span data-stu-id="e62d9-124">This is how the rows in the universal table are processed to produce the resulting XML tree:</span></span>  
  
 <span data-ttu-id="e62d9-125">La prima riga identifica il valore `Tag` come `1`.</span><span class="sxs-lookup"><span data-stu-id="e62d9-125">The first row identifies `Tag` value `1`.</span></span> <span data-ttu-id="e62d9-126">Viene pertanto identificato il gruppo di colonne con il valore `Tag` di `1` , `Employee!1!EmpID`.</span><span class="sxs-lookup"><span data-stu-id="e62d9-126">Therefore, the column group that has the `Tag` value `1` is identified, `Employee!1!EmpID`.</span></span> <span data-ttu-id="e62d9-127">Questa colonna identifica `Employee` come nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e62d9-127">This column identifies `Employee` as the element name.</span></span> <span data-ttu-id="e62d9-128">Viene quindi creato un elemento <`Employee`> con attributi `EmpID`.</span><span class="sxs-lookup"><span data-stu-id="e62d9-128">An <`Employee`> element is then created that has `EmpID` attributes.</span></span> <span data-ttu-id="e62d9-129">A questi attributi vengono assegnati i valori di colonna corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e62d9-129">Corresponding column values are assigned to these attributes.</span></span>  
  
 <span data-ttu-id="e62d9-130">La seconda riga ha il valore `Tag` di `2`.</span><span class="sxs-lookup"><span data-stu-id="e62d9-130">The second row has the `Tag` value `2`.</span></span> <span data-ttu-id="e62d9-131">Viene pertanto identificato il gruppo di colonne con il valore `Tag` di `2` nel nome della colonna, `Name!2!FName`, `Name!2!LName`.</span><span class="sxs-lookup"><span data-stu-id="e62d9-131">Therefore, the column group that has the `Tag` value `2` in the column name, `Name!2!FName`, `Name!2!LName`, is identified.</span></span> <span data-ttu-id="e62d9-132">Questi nomi di colonna identificano `Name` come nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e62d9-132">These column names identify `Name` as element name.</span></span> <span data-ttu-id="e62d9-133">Viene creato un elemento <`Name`> con attributi `FName` e `LName`.</span><span class="sxs-lookup"><span data-stu-id="e62d9-133">A <`Name`> element is created that has `FName` and `LName` attributes.</span></span> <span data-ttu-id="e62d9-134">A questi attributi vengono quindi assegnati i valori di colonna corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e62d9-134">Corresponding column values are then assigned to these attributes.</span></span> <span data-ttu-id="e62d9-135">Questa riga identifica `1` come valore di `Parent`.</span><span class="sxs-lookup"><span data-stu-id="e62d9-135">This row identifies `1` as `Parent`.</span></span> <span data-ttu-id="e62d9-136">Questo elemento figlio viene aggiunto all'elemento <`Employee`> precedente.</span><span class="sxs-lookup"><span data-stu-id="e62d9-136">This element child is added to the previous <`Employee`> element.</span></span>  
  
 <span data-ttu-id="e62d9-137">Il processo viene ripetuto per tutte le righe del set di righe.</span><span class="sxs-lookup"><span data-stu-id="e62d9-137">This process is repeated for rest of the rows in the rowset.</span></span> <span data-ttu-id="e62d9-138">Si noti l'importanza dell'ordinamento delle righe nella tabella universale, in modo che l'istruzione FOR XML EXPLICIT possa elaborare il set di righe nell'ordine corretto e generare il codice XML desiderato.</span><span class="sxs-lookup"><span data-stu-id="e62d9-138">Note the importance of ordering the rows in the universal table so that FOR XML EXPLICIT can process the rowset in order and generate the XML you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62d9-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e62d9-139">See Also</span></span>  
 [<span data-ttu-id="e62d9-140">Usare la modalità EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="e62d9-140">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
