---
title: Usare la modalità AUTO con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, AUTO mode
- ELEMENTS option
- FOR XML AUTO mode
- AUTO FOR XML mode
ms.assetid: 7140d656-1d42-4f01-a533-5251429f4450
author: rothja
ms.author: jroth
ms.openlocfilehash: 232cc046667c6d31cb9657a7abdc862204507d23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629269"
---
# <a name="use-auto-mode-with-for-xml"></a><span data-ttu-id="77f97-102">Utilizzo della modalità AUTO con FOR XML</span><span class="sxs-lookup"><span data-stu-id="77f97-102">Use AUTO Mode with FOR XML</span></span>
  <span data-ttu-id="77f97-103">Come descritto in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), la modalità AUTO restituisce i risultati della query come elementi XML annidati.</span><span class="sxs-lookup"><span data-stu-id="77f97-103">As described in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), AUTO mode returns query results as nested XML elements.</span></span> <span data-ttu-id="77f97-104">ma non consente di controllare in modo preciso la struttura del valore XML generato.</span><span class="sxs-lookup"><span data-stu-id="77f97-104">This does not provide much control over the shape of the XML generated from a query result.</span></span> <span data-ttu-id="77f97-105">È consigliabile utilizzare query in modalità AUTO solo se si desidera generare gerarchie semplici.</span><span class="sxs-lookup"><span data-stu-id="77f97-105">The AUTO mode queries are useful if you want to generate simple hierarchies.</span></span> <span data-ttu-id="77f97-106">Tuttavia, l' [uso della modalità EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md) e l' [uso della modalità PATH con FOR XML](use-path-mode-with-for-xml.md) assicurano maggiore controllo e flessibilità nella definizione della forma di elementi XML dal risultato di una query.</span><span class="sxs-lookup"><span data-stu-id="77f97-106">However, [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) and [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) provide more control and flexibility in deciding the shape of the XML from a query result.</span></span>  
  
 <span data-ttu-id="77f97-107">Ogni tabella nella clausola FROM, della quale almeno una colonna viene elencata nella clausola SELECT, viene rappresentata come un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="77f97-107">Each table in the FROM clause, from which at least one column is listed in the SELECT clause, is represented as an XML element.</span></span> <span data-ttu-id="77f97-108">Se per la clausola FOR XML è specificata l'opzione facoltativa ELEMENTS, verrà eseguito il mapping delle colonne elencate nella clausola SELECT ad attributi o sottoelementi.</span><span class="sxs-lookup"><span data-stu-id="77f97-108">The columns listed in the SELECT clause are mapped to attributes or subelements, if the optional ELEMENTS option is specified in the FOR XML clause.</span></span>  
  
 <span data-ttu-id="77f97-109">La gerarchia XML (nidificazione degli elementi) del valore XML risultante è basata sull'ordine delle tabelle identificate dalle colonne specificate nella clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="77f97-109">The XML hierarchy, nesting of the elements, in the resulting XML is based on the order of tables identified by the columns specified in the SELECT clause.</span></span> <span data-ttu-id="77f97-110">L'ordine in cui sono specificati i nomi delle colonne nella clausola SELECT è pertanto significativo.</span><span class="sxs-lookup"><span data-stu-id="77f97-110">Therefore, the order in which column names are specified in the SELECT clause is significant.</span></span> <span data-ttu-id="77f97-111">La prima tabella da sinistra identificata costituisce l'elemento di livello principale nel documento XML risultante.</span><span class="sxs-lookup"><span data-stu-id="77f97-111">The first, leftmost table that is identified forms the top element in the resulting XML document.</span></span> <span data-ttu-id="77f97-112">La seconda tabella da sinistra, identificata dalle colonne nell'istruzione SELECT, costituisce un sottoelemento all'interno dell'elemento di livello principale e così via.</span><span class="sxs-lookup"><span data-stu-id="77f97-112">The second leftmost table, identified by columns in the SELECT statement, forms a subelement within the top element, and so on.</span></span>  
  
 <span data-ttu-id="77f97-113">Se un nome di colonna elencato nella clausola SELECT appartiene a una tabella già identificata da una colonna specificata in precedenza nella clausola SELECT, tale colonna verrà aggiunta come attributo dell'elemento già creato, anziché aggiungere un nuovo livello alla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="77f97-113">If a column name listed in the SELECT clause is from a table that is already identified by a previously specified column in the SELECT clause, the column is added as an attribute of the element already created, instead of opening a new level of hierarchy.</span></span> <span data-ttu-id="77f97-114">Se si specifica l'opzione ELEMENTS, la colonna verrà aggiunta come attributo.</span><span class="sxs-lookup"><span data-stu-id="77f97-114">If the ELEMENTS option is specified, the column is added as an attribute.</span></span>  
  
 <span data-ttu-id="77f97-115">Si esegua ad esempio la query seguente:</span><span class="sxs-lookup"><span data-stu-id="77f97-115">For example, execute this query:</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO  
```  
  
 <span data-ttu-id="77f97-116">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="77f97-116">This is the partial result:</span></span>  
  
```  
<Cust CustomerID="1" CustomerType="S">  
  <OrderHeader CustomerID="1" SalesOrderID="43860" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="44501" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="45283" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="46042" Status="5" />  
</Cust>  
...  
```  
  
 <span data-ttu-id="77f97-117">Nella clausola SELECT si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="77f97-117">Note the following in the SELECT clause:</span></span>  
  
-   <span data-ttu-id="77f97-118">CustomerID fa riferimento alla tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="77f97-118">The CustomerID references the Cust table.</span></span> <span data-ttu-id="77f97-119">Verrà pertanto creato un elemento <`Cust`> al quale verrà aggiunto CustomerID come attributo.</span><span class="sxs-lookup"><span data-stu-id="77f97-119">Therefore, a <`Cust`> element is created and CustomerID is added as its attribute.</span></span>  
  
-   <span data-ttu-id="77f97-120">Poiché inoltre le tre colonne OrderHeader.CustomerID, OrderHeader.SaleOrderID e OrderHeader.Status fanno riferimento alla tabella OrderHeader,</span><span class="sxs-lookup"><span data-stu-id="77f97-120">Next, three columns, OrderHeader.CustomerID, OrderHeader.SaleOrderID, and OrderHeader.Status, reference the OrderHeader table.</span></span> <span data-ttu-id="77f97-121">viene aggiunto un elemento <`OrderHeader`> come sottoelemento dell'elemento <`Cust`> e le tre colonne vengono aggiunte come attributi di <`OrderHeader`>.</span><span class="sxs-lookup"><span data-stu-id="77f97-121">Therefore, an <`OrderHeader`> element is added as a subelement of the <`Cust`> element and the three columns are added as attributes of <`OrderHeader`>.</span></span>  
  
-   <span data-ttu-id="77f97-122">Anche la colonna Cust.CustomerType fa riferimento alla tabella Cust, che era già stata identificata dalla colonna Cust.CustomerID.</span><span class="sxs-lookup"><span data-stu-id="77f97-122">Next, the Cust.CustomerType column again references the Cust table that was already identified by the Cust.CustomerID column.</span></span> <span data-ttu-id="77f97-123">Non verranno pertanto creati nuovi elementi,</span><span class="sxs-lookup"><span data-stu-id="77f97-123">Therefore, no new element is created.</span></span> <span data-ttu-id="77f97-124">ma all'elemento <`Cust`> creato in precedenza verrà aggiunto l'attributo CustomerType.</span><span class="sxs-lookup"><span data-stu-id="77f97-124">Instead, the CustomerType attribute is added to the <`Cust`> element that was previously created.</span></span>  
  
-   <span data-ttu-id="77f97-125">Nella query sono specificati alias per i nomi delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="77f97-125">The query specifies aliases for the table names.</span></span> <span data-ttu-id="77f97-126">Tali alias sono i nomi degli elementi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="77f97-126">These aliases appear as corresponding element names.</span></span>  
  
-   <span data-ttu-id="77f97-127">La clausola ORDER BY è necessaria per raggruppare tutti gli elementi figlio sotto un unico elemento padre.</span><span class="sxs-lookup"><span data-stu-id="77f97-127">ORDER BY is required to group all children under one parent.</span></span>  
  
 <span data-ttu-id="77f97-128">Questa query è simile alla precedente, con la differenza che nella clausola SELECT le colonne della tabella OrderHeader sono specificate prima di quelle della tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="77f97-128">This query is similar to the previous one, except the SELECT clause specifies columns in the OrderHeader table before the columns in the Cust table.</span></span> <span data-ttu-id="77f97-129">Viene pertanto creato prima l'elemento <`OrderHeader`>, a cui viene aggiunto l'elemento figlio <`Cust`>.</span><span class="sxs-lookup"><span data-stu-id="77f97-129">Therefore, first <`OrderHeader`> element is created and then the <`Cust`> child element is added to it.</span></span>  
  
```  
select OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerID,   
       Cust.CustomerType  
from Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
where Cust.CustomerID = OrderHeader.CustomerID  
for xml auto  
```  
  
 <span data-ttu-id="77f97-130">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="77f97-130">This is the partial result:</span></span>  
  
```  
<OrderHeader CustomerID="1" SalesOrderID="43860" Status="5">  
  <Cust CustomerID="1" CustomerType="S" />  
</OrderHeader>  
...  
```  
  
 <span data-ttu-id="77f97-131">Se alla clausola FOR XML viene aggiunta l'opzione ELEMENTS, verrà restituito un valore XML incentrato sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="77f97-131">If the ELEMENTS option is added in the FOR XML clause, element-centric XML is returned.</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="77f97-132">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="77f97-132">This is the partial result:</span></span>  
  
```  
<Cust>  
  <CustomerID>1</CustomerID>  
  <CustomerType>S</CustomerType>  
  <OrderHeader>  
    <CustomerID>1</CustomerID>  
    <SalesOrderID>43860</SalesOrderID>  
    <Status>5</Status>  
  </OrderHeader>  
   ...  
</Cust>  
...  
```  
  
 <span data-ttu-id="77f97-133">In questa query, durante la creazione degli elementi \<Cust>, i valori CustomerID di ogni riga vengono confrontati con quelli della riga successiva perché CustomerID è la chiave primaria della tabella.</span><span class="sxs-lookup"><span data-stu-id="77f97-133">In this query, the CustomerID values are compared from one row to the next in creating the \<Cust> elements, because CustomerID is the primary key of the table.</span></span> <span data-ttu-id="77f97-134">Se CustomerID non viene identificata come chiave primaria della tabella, tutti i valori delle colonne (in questa query, CustomerID e CustomerType) di ogni riga verranno confrontati con quelli della riga successiva.</span><span class="sxs-lookup"><span data-stu-id="77f97-134">If CustomerID is not identified as the primary key for the table, all the column values (CustomerID, CustomerType in this query) are compared from one row to the next.</span></span> <span data-ttu-id="77f97-135">Se i valori sono diversi, al valore XML verrà aggiunto un nuovo elemento \<Cust>.</span><span class="sxs-lookup"><span data-stu-id="77f97-135">If the values differ, a new \<Cust> element is added to the XML.</span></span>  
  
 <span data-ttu-id="77f97-136">Durante il confronto di questi valori di colonna, se una qualsiasi delle colonne da confrontare è di tipo **text**, **ntext**, **image**o **xml**, FOR XML presupporrà che i valori siano diversi e non eseguirà il confronto, anche se potrebbero essere uguali.</span><span class="sxs-lookup"><span data-stu-id="77f97-136">When comparing these column values, if any of the columns to be compared are of type **text**, **ntext**, **image**, or **xml**, FOR XML assumes that the values are different and not compared, even though they may be the same.</span></span> <span data-ttu-id="77f97-137">Questo avviene perché il confronto di oggetti di grandi dimensioni non è supportato.</span><span class="sxs-lookup"><span data-stu-id="77f97-137">This is because comparing large objects is not supported.</span></span> <span data-ttu-id="77f97-138">Vengono aggiunti elementi al risultato per ogni riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="77f97-138">Elements are added to the result for each row selected.</span></span> <span data-ttu-id="77f97-139">Si noti che le colonne di tipo **(n)varchar(max)** e **varbinary(max)** vengono confrontate.</span><span class="sxs-lookup"><span data-stu-id="77f97-139">Note that columns of **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="77f97-140">Quando una colonna nella clausola SELECT non può essere associata a una qualsiasi delle tabelle identificate nella clausola FROM, ad esempio nel caso di una colonna aggregata o calcolata, la colonna viene aggiunta al documento XML al livello di nidificazione più basso quando viene rilevata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="77f97-140">When a column in the SELECT clause cannot be associated with any of the tables identified in the FROM clause, as in the case of an aggregate column or computed column, the column is added in the XML document in the deepest nesting level in place when it is encountered in the list.</span></span> <span data-ttu-id="77f97-141">Se tale colonna viene elencata per prima nella clausola SELECT, verrà aggiunta come elemento di livello principale.</span><span class="sxs-lookup"><span data-stu-id="77f97-141">If such a column appears as the first column in the SELECT clause, the column is added to the top element.</span></span>  
  
 <span data-ttu-id="77f97-142">Se nella clausola SELECT è specificato il carattere jolly asterisco (\*), il livello di nidificazione verrà determinato come descritto in precedenza, ovvero in base all'ordine in cui le righe vengono restituite dal motore query.</span><span class="sxs-lookup"><span data-stu-id="77f97-142">If the asterisk (\*) wildcard character is specified in the SELECT clause, the nesting is determined in the same way as previously described, based on the order that the rows are returned by the query engine.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77f97-143">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="77f97-143">In This Section</span></span>  
 <span data-ttu-id="77f97-144">Per ulteriori informazioni sulla modalità AUTO, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="77f97-144">The following topics provide more information about AUTO mode:</span></span>  
  
-   [<span data-ttu-id="77f97-145">Usare l'opzione BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="77f97-145">Use the BINARY BASE64 Option</span></span>](use-the-binary-base64-option.md)  
  
-   [<span data-ttu-id="77f97-146">Approccio euristico della modalità AUTO per la determinazione della struttura dei valori XML restituiti</span><span class="sxs-lookup"><span data-stu-id="77f97-146">AUTO Mode Heuristics in Shaping Returned XML</span></span>](auto-mode-heuristics-in-shaping-returned-xml.md)  
  
-   [<span data-ttu-id="77f97-147">Esempi: Utilizzo della modalità AUTO</span><span class="sxs-lookup"><span data-stu-id="77f97-147">Examples: Using AUTO Mode</span></span>](examples-using-auto-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="77f97-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77f97-148">See Also</span></span>  
 <span data-ttu-id="77f97-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77f97-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="77f97-150">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77f97-150">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
