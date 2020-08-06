---
title: Generare elementi di pari livello tramite query annidate in modalità AUTO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- queries [XML in SQL Server], nested AUTO mode
- nested AUTO mode query
ms.assetid: 748d9899-589d-4420-8048-1258e9e67c20
author: rothja
ms.author: jroth
ms.openlocfilehash: 20362942bdd0f7e7537433b664e5e63461ded499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726740"
---
# <a name="generate-siblings-with-a-nested-auto-mode-query"></a><span data-ttu-id="d8eee-102">Generare elementi di pari livello tramite query nidificate in modalità AUTO</span><span class="sxs-lookup"><span data-stu-id="d8eee-102">Generate Siblings with a Nested AUTO Mode Query</span></span>
  <span data-ttu-id="d8eee-103">Nell'esempio seguente viene descritta la procedura per generare elementi di pari livello tramite una query nidificata in modalità AUTO.</span><span class="sxs-lookup"><span data-stu-id="d8eee-103">The following example shows how to generate siblings by using a nested AUTO mode query.</span></span> <span data-ttu-id="d8eee-104">L'unico metodo alternativo per generare un valore XML di questo tipo è utilizzare la modalità EXPLICIT,</span><span class="sxs-lookup"><span data-stu-id="d8eee-104">The only other way to generate such XML is to use the EXPLICIT mode.</span></span> <span data-ttu-id="d8eee-105">ma ciò può rivelarsi eccessivamente complesso.</span><span class="sxs-lookup"><span data-stu-id="d8eee-105">However, this can be cumbersome.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8eee-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8eee-106">Example</span></span>  
 <span data-ttu-id="d8eee-107">Questa query costruisce un valore XML che contiene informazioni sugli ordini di vendita,</span><span class="sxs-lookup"><span data-stu-id="d8eee-107">This query constructs XML that provides sales order information.</span></span> <span data-ttu-id="d8eee-108">Sono inclusi gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8eee-108">This includes the following:</span></span>  
  
-   <span data-ttu-id="d8eee-109">Informazioni contenute nell'intestazione degli ordini di vendita, `SalesOrderID`, `SalesPersonID`e `OrderDate`.</span><span class="sxs-lookup"><span data-stu-id="d8eee-109">Sales order header information, `SalesOrderID`, `SalesPersonID`, and `OrderDate`.</span></span> [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="d8eee-110">archivia queste informazioni nella tabella `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-110">stores this information in the `SalesOrderHeader` table.</span></span>  
  
-   <span data-ttu-id="d8eee-111">Informazioni dettagliate sugli ordini di vendita,</span><span class="sxs-lookup"><span data-stu-id="d8eee-111">Sales order detail information.</span></span> <span data-ttu-id="d8eee-112">che includono i prodotti ordinati, il prezzo unitario e la quantità ordinata.</span><span class="sxs-lookup"><span data-stu-id="d8eee-112">This includes one or more products ordered, the unit price, and the quantity ordered.</span></span> <span data-ttu-id="d8eee-113">Tali informazioni sono archiviate nella tabella `SalesOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-113">This information is stored in the `SalesOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="d8eee-114">Informazioni sul venditore,</span><span class="sxs-lookup"><span data-stu-id="d8eee-114">Sales person information.</span></span> <span data-ttu-id="d8eee-115">ovvero la persona che ha ricevuto l'ordine.</span><span class="sxs-lookup"><span data-stu-id="d8eee-115">This is the salesperson who took the order.</span></span> <span data-ttu-id="d8eee-116">Il codice `SalesPerson` è archiviato nella tabella `SalesPersonID`.</span><span class="sxs-lookup"><span data-stu-id="d8eee-116">The `SalesPerson` table provides the `SalesPersonID`.</span></span> <span data-ttu-id="d8eee-117">Per questa query è necessario unire in join tale tabella con la tabella `Employee` , per trovare il nome del venditore.</span><span class="sxs-lookup"><span data-stu-id="d8eee-117">For this query, you have to join this table to the `Employee` table to find the name of the sales person.</span></span>  
  
 <span data-ttu-id="d8eee-118">Le due query `SELECT` che seguono generano valori XML con struttura lievemente diversa.</span><span class="sxs-lookup"><span data-stu-id="d8eee-118">The two distinct `SELECT` queries that follow generate XML with a small difference in shape.</span></span>  
  
 <span data-ttu-id="d8eee-119">La prima query genera un valore XML in cui <`SalesPerson`> e <`SalesOrderHeader`> sono elementi di pari livello figli di <`SalesOrder`>:</span><span class="sxs-lookup"><span data-stu-id="d8eee-119">The first query generates XML in which <`SalesPerson`> and <`SalesOrderHeader`> appear as sibling children of <`SalesOrder`>:</span></span>  
  
```  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID =   
                   SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
        FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
        for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As   
                     SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="d8eee-120">Nella query precedente l'istruzione `SELECT` più esterna esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8eee-120">In the previous query, the outermost `SELECT` statement does the following:</span></span>  
  
-   <span data-ttu-id="d8eee-121">Esegue una query sul set di righe `SalesOrder`, specificato nella clausola `FROM`.</span><span class="sxs-lookup"><span data-stu-id="d8eee-121">Queries the rowset, `SalesOrder`, specified in the `FROM` clause.</span></span> <span data-ttu-id="d8eee-122">Viene restituito un valore XML con uno o più elementi <`SalesOrder`>.</span><span class="sxs-lookup"><span data-stu-id="d8eee-122">The result is an XML with one or more <`SalesOrder`> elements.</span></span>  
  
-   <span data-ttu-id="d8eee-123">Specifica la modalità `AUTO` e la direttiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-123">Specifies `AUTO` mode and the `TYPE` directive.</span></span> <span data-ttu-id="d8eee-124">`AUTO`la modalità trasforma il risultato della query in XML e la `TYPE` direttiva restituisce il risultato come `xml` tipo.</span><span class="sxs-lookup"><span data-stu-id="d8eee-124">`AUTO` mode transforms the query result into XML, and the `TYPE` directive returns the result as `xml` type.</span></span>  
  
-   <span data-ttu-id="d8eee-125">Include due istruzioni `SELECT` nidificate, separate da una virgola (,).</span><span class="sxs-lookup"><span data-stu-id="d8eee-125">Includes two nested `SELECT` statements separated by a comma.</span></span> <span data-ttu-id="d8eee-126">La prima istruzione nidificata `SELECT` recupera le informazioni relative all'ordine di vendita, l'intestazione ed i dettagli, mentre la seconda istruzione `SELECT` recupera le informazioni relative al venditore.</span><span class="sxs-lookup"><span data-stu-id="d8eee-126">The first nested `SELECT` retrieves sales order information, header and details, and the second nested `SELECT` statement retrieves salesperson information.</span></span>  
  
    -   <span data-ttu-id="d8eee-127">L'istruzione `SELECT` che recupera `SalesOrderID`, `SalesPersonID`e `CustomerID` include a sua volta un'altra istruzione nidificata `SELECT ... FOR XML` (con modalità `AUTO` e direttiva `TYPE` ), che restituisce i dettagli dell'ordine di vendita.</span><span class="sxs-lookup"><span data-stu-id="d8eee-127">The `SELECT` statement that retrieves `SalesOrderID`, `SalesPersonID`, and `CustomerID` itself includes another nested `SELECT ... FOR XML` statement (with `AUTO` mode and `TYPE` directive) that returns sales order detail information.</span></span>  
  
 <span data-ttu-id="d8eee-128">L'istruzione `SELECT` che recupera le informazioni relative al venditore esegue una query sul set di righe `SalesPerson`, creato nella clausola `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-128">The `SELECT` statement that retrieves the sales person information queries a rowset, `SalesPerson`, created in the `FROM` clause.</span></span> <span data-ttu-id="d8eee-129">Per consentire l'esecuzione delle query `FOR XML` , è necessario specificare un nome per il set di righe anonimo generato nella clausola `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-129">For `FOR XML` queries to work, you must provide a name for the anonymous rowset generated in the `FROM` clause.</span></span> <span data-ttu-id="d8eee-130">In tal caso viene specificato il nome `SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="d8eee-130">In this case, the name provided is `SalesPerson`.</span></span>  
  
 <span data-ttu-id="d8eee-131">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="d8eee-131">This is the partial result:</span></span>  
  
```  
<SalesOrder>  
  <Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  </Sales.SalesOrderHeader>  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</SalesOrder>  
...  
```  
  
 <span data-ttu-id="d8eee-132">La query seguente genera le stesse informazioni relative all'ordine di vendita, con la differenza che nel valore XML risultante <`SalesPerson`> appare un elemento di pari livello di <`SalesOrderDetail`>:</span><span class="sxs-lookup"><span data-stu-id="d8eee-132">The following query generates the same sales order information, except that in the resulting XML, the <`SalesPerson`> appears as a sibling of <`SalesOrderDetail`>:</span></span>  
  
```  
<SalesOrder>  
    <SalesOrderHeader ...>  
          <SalesOrderDetail .../>  
          <SalesOrderDetail .../>  
          ...  
          <SalesPerson .../>  
    </SalesOrderHeader>  
  
</SalesOrder>  
<SalesOrder>  
  ...  
</SalesOrder>  
```  
  
 <span data-ttu-id="d8eee-133">Query:</span><span class="sxs-lookup"><span data-stu-id="d8eee-133">This is the query:</span></span>  
  
```  
SELECT SalesOrderID, SalesPersonID, CustomerID,  
             (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
              from Sales.SalesOrderDetail  
              WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
              FOR XML AUTO, TYPE),  
              (SELECT *   
               FROM  (SELECT SalesPersonID, EmployeeID  
                    FROM Sales.SalesPerson, HumanResources.Employee  
                    WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
               WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
         FOR XML AUTO, TYPE)  
FROM Sales.SalesOrderHeader  
WHERE SalesOrderID=43659 or SalesOrderID=43660  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="d8eee-134">Risultato:</span><span class="sxs-lookup"><span data-stu-id="d8eee-134">This is the result:</span></span>  
  
```  
<Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
<Sales.SalesOrderHeader SalesOrderID="43660" SalesPersonID="279" CustomerID="117">  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="762" OrderQty="1" UnitPrice="419.4589" />  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="758" OrderQty="1" UnitPrice="874.7940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
```  
  
 <span data-ttu-id="d8eee-135">Poiché la direttiva `TYPE` restituisce il risultato della query come tipo `xml`, è possibile eseguire una query sul valore XML risultante utilizzando vari metodi con tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="d8eee-135">Because the `TYPE` directive returns a query result as `xml` type, you can query the resulting XML by using various `xml` data type methods.</span></span> <span data-ttu-id="d8eee-136">Per altre informazioni, vedere [Metodi con tipo di dati XML](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="d8eee-136">For more information, see [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span> <span data-ttu-id="d8eee-137">In questa query di esempio, si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d8eee-137">In the following query, note the following:</span></span>  
  
-   <span data-ttu-id="d8eee-138">La query precedente viene aggiunta nella clausola `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-138">The previous query is added in the `FROM` clause.</span></span> <span data-ttu-id="d8eee-139">Il risultato della query viene restituito sotto forma di tabella.</span><span class="sxs-lookup"><span data-stu-id="d8eee-139">The query result is returned as a table.</span></span> <span data-ttu-id="d8eee-140">Viene aggiunto l'alias `XmlCol` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-140">Note the `XmlCol` alias that is added.</span></span>  
  
-   <span data-ttu-id="d8eee-141">La clausola `SELECT` specifica una query XQuery sul valore `XmlCol` restituito nella clausola `FROM` .</span><span class="sxs-lookup"><span data-stu-id="d8eee-141">The `SELECT` clause specifies an XQuery against the `XmlCol` returned in the `FROM` clause.</span></span> <span data-ttu-id="d8eee-142">Per specificare la query XQuery viene utilizzato il metodo `query()` con tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="d8eee-142">The `query()` method of the `xml` data type is used in specifying the XQuery.</span></span> <span data-ttu-id="d8eee-143">Per altre informazioni, vedere [Metodo query&#40;&#41; con &#40;tipo di dati XML&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="d8eee-143">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
    ```  
    SELECT XmlCol.query('<Root> { /* } </Root>')  
    FROM (  
    SELECT SalesOrderID, SalesPersonID, CustomerID,  
                 (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
                  from Sales.SalesOrderDetail  
                  WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
                  FOR XML AUTO, TYPE),  
                  (SELECT *   
                   FROM  (SELECT SalesPersonID, EmployeeID  
                        FROM Sales.SalesPerson, HumanResources.Employee  
                        WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
                   WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
             FOR XML AUTO, TYPE)  
    FROM Sales.SalesOrderHeader  
    WHERE SalesOrderID='43659' or SalesOrderID='43660'  
    FOR XML AUTO, TYPE ) as T(XmlCol)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8eee-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8eee-144">See Also</span></span>  
 [<span data-ttu-id="d8eee-145">Utilizzo di query FOR XML nidificate</span><span class="sxs-lookup"><span data-stu-id="d8eee-145">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
