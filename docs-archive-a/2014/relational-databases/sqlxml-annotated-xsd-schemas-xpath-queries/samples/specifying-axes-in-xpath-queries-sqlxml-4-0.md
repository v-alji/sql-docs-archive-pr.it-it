---
title: Specifica di assi in query XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- context node [SQLXML]
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- axes [SQLXML]
ms.assetid: d17b8278-da58-4576-95b4-7a92772566d8
author: rothja
ms.author: jroth
ms.openlocfilehash: f6f17404ea109bb0e687f9116b61025bbc411008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623995"
---
# <a name="specifying-axes-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="70385-102">Definizione di assi in query XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="70385-102">Specifying Axes in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="70385-103">Negli esempi seguenti viene illustrato il modo in cui specificare assi in query XPath.</span><span class="sxs-lookup"><span data-stu-id="70385-103">The following examples show how axes are specified in XPath queries.</span></span>  
  
 <span data-ttu-id="70385-104">Le query XPath di questi esempi vengono specificate sullo schema di mapping contenuto in SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="70385-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="70385-105">Per informazioni su questo schema di esempio, vedere [schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="70385-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="70385-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="70385-106">Examples</span></span>  
  
### <a name="a-retrieve-child-elements-of-the-context-node"></a><span data-ttu-id="70385-107">R.</span><span class="sxs-lookup"><span data-stu-id="70385-107">A.</span></span> <span data-ttu-id="70385-108">Recuperare elementi figlio del nodo di contesto</span><span class="sxs-lookup"><span data-stu-id="70385-108">Retrieve child elements of the context node</span></span>  
 <span data-ttu-id="70385-109">La query XPath seguente seleziona tutti gli **\<Contact>** elementi figlio del nodo di contesto:</span><span class="sxs-lookup"><span data-stu-id="70385-109">The following XPath query selects all the **\<Contact>** child elements of the context node:</span></span>  
  
```  
/child::Contact  
```  
  
 <span data-ttu-id="70385-110">Nella query `child` è l'asse e `Contact` è il test di nodo (true se `Contact` è un **\<element>** nodo, perché \<element> è il tipo di nodo primario associato all' `child` asse).</span><span class="sxs-lookup"><span data-stu-id="70385-110">In the query, `child` is the axis and `Contact` is the node test (TRUE if `Contact` is an **\<element>** node, because \<element> is the primary node type associated with the `child` axis).</span></span>  
  
 <span data-ttu-id="70385-111">L'asse `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="70385-111">The `child` axis is the default.</span></span> <span data-ttu-id="70385-112">È pertanto possibile scrivere la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="70385-112">Therefore, the query can be written as:</span></span>  
  
```  
/Contact  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="70385-113">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="70385-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="70385-114">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="70385-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="70385-115">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="70385-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="70385-116">Creare il modello seguente (XPathAxesSampleA.xml) e salvarlo nella directory in cui è stato salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="70385-116">Create the following template (XPathAxesSampleA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="70385-117">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="70385-118">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="70385-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="70385-119">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="70385-120">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="70385-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="70385-121">Di seguito viene indicato il set di risultati parziale dell'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="70385-121">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Contact ContactID="1" LastName="Achong" FirstName="Gustavo" Title="Mr." />   
  <Contact ContactID="2" LastName="Abel" FirstName="Catherine" Title="Ms." />   
  <Contact ContactID="3" LastName="Abercrombie" FirstName="Kim" Title="Ms." />   
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />  
  ...  
</ROOT>  
```  
  
### <a name="b-retrieve-grandchildren-of-the-context-node"></a><span data-ttu-id="70385-122">B.</span><span class="sxs-lookup"><span data-stu-id="70385-122">B.</span></span> <span data-ttu-id="70385-123">Recuperare nipoti del nodo di contesto</span><span class="sxs-lookup"><span data-stu-id="70385-123">Retrieve grandchildren of the context node</span></span>  
 <span data-ttu-id="70385-124">La query XPath seguente seleziona tutti gli **\<Order>** elementi figlio degli **\<Customer>** elementi figlio del nodo di contesto:</span><span class="sxs-lookup"><span data-stu-id="70385-124">The following XPath query selects all the **\<Order>** element children of the **\<Customer>** element children of the context node:</span></span>  
  
```  
/child::Customer/child::Order  
```  
  
 <span data-ttu-id="70385-125">Nella query `child` è l'asse e `Customer` e `Order` sono i test di nodo (i test del nodo sono true se Customer e Order sono **\<element>** nodi, perché il **\<element>** nodo è il nodo primario per l' `child` asse).</span><span class="sxs-lookup"><span data-stu-id="70385-125">In the query, `child` is the axis and `Customer` and `Order` are the node tests (these node tests are TRUE if Customer and Order are **\<element>** nodes, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="70385-126">Per ogni nodo corrispondente **\<Customer>** , i nodi corrispondenti **\<Orders>** vengono aggiunti al risultato.</span><span class="sxs-lookup"><span data-stu-id="70385-126">For each node matching **\<Customer>**, the nodes matching **\<Orders>** are added to the result.</span></span> <span data-ttu-id="70385-127">**\<Order>** Nel set di risultati viene restituito solo.</span><span class="sxs-lookup"><span data-stu-id="70385-127">Only **\<Order>** is returned in the result set.</span></span>  
  
 <span data-ttu-id="70385-128">L'asse `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="70385-128">The `child` axis is the default.</span></span> <span data-ttu-id="70385-129">È pertanto possibile specificare la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="70385-129">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="70385-130">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="70385-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="70385-131">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="70385-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="70385-132">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="70385-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="70385-133">Creare il modello seguente (XPathAxesSampleB.xml) e salvarlo nella directory in cui:</span><span class="sxs-lookup"><span data-stu-id="70385-133">Create the following template (XPathAxesSampleB.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="70385-134">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="70385-135">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="70385-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="70385-136">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="70385-137">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="70385-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="70385-138">Di seguito viene indicato il set di risultati parziale dell'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="70385-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</ROOT>  
```  
  
 <span data-ttu-id="70385-139">Se la query XPath è specificata come `Customer/Order/OrderDetail` , da ogni nodo che corrisponde **\<Customer>** alla query passa ai relativi **\<Order>** elementi.</span><span class="sxs-lookup"><span data-stu-id="70385-139">If the XPath query is specified as `Customer/Order/OrderDetail`, from each node matching **\<Customer>** the query navigates to its **\<Order>** elements.</span></span> <span data-ttu-id="70385-140">Per ogni nodo corrispondente **\<Order>** , la query aggiunge i nodi **\<OrderDetail>** al risultato.</span><span class="sxs-lookup"><span data-stu-id="70385-140">And for each node matching **\<Order>**, the query adds the nodes **\<OrderDetail>** to the result.</span></span> <span data-ttu-id="70385-141">**\<OrderDetail>** Nel set di risultati viene restituito solo.</span><span class="sxs-lookup"><span data-stu-id="70385-141">Only **\<OrderDetail>** is returned in the result set.</span></span>  
  
### <a name="c-use--to-specify-the-parent-axis"></a><span data-ttu-id="70385-142">C.</span><span class="sxs-lookup"><span data-stu-id="70385-142">C.</span></span> <span data-ttu-id="70385-143">Utilizzare .</span><span class="sxs-lookup"><span data-stu-id="70385-143">Use ..</span></span> <span data-ttu-id="70385-144">per specificare l'asse padre</span><span class="sxs-lookup"><span data-stu-id="70385-144">to specify the parent axis</span></span>  
 <span data-ttu-id="70385-145">La query seguente recupera tutti gli **\<Order>** elementi con un **\<Customer>** elemento padre con il valore di attributo **CustomerID** 1.</span><span class="sxs-lookup"><span data-stu-id="70385-145">The following query retrieves all the **\<Order>** elements with a parent **\<Customer>** element with a **CustomerID** attribute value of 1.</span></span> <span data-ttu-id="70385-146">La query utilizza l' `child` asse nel predicato per trovare il padre dell' **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="70385-146">The query uses the `child` axis in the predicate to find the parent of the **\<Order>** element.</span></span>  
  
```  
/child::Customer/child::Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="70385-147">L'asse `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="70385-147">The `child` axis is the default axis.</span></span> <span data-ttu-id="70385-148">È pertanto possibile specificare la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="70385-148">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="70385-149">La query XPath è equivalente a:</span><span class="sxs-lookup"><span data-stu-id="70385-149">The XPath query is equivalent to:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="70385-150">La query XPath `/Order[../@CustomerID="1"]` restituirà un errore perché non è presente alcun elemento padre di **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="70385-150">The XPath query `/Order[../@CustomerID="1"]` will return an error because there is no parent of **\<Order>**.</span></span> <span data-ttu-id="70385-151">Sebbene possano essere presenti elementi nello schema di mapping che contengono **\<Order>** , XPath non è iniziato in corrispondenza di alcuno di essi, di conseguenza **\<Order>** viene considerato il tipo di elemento di primo livello nel documento.</span><span class="sxs-lookup"><span data-stu-id="70385-151">Although there may be elements in the mapping schema that contain **\<Order>**, the XPath did not begin at any of them; consequently, **\<Order>** is considered to be the top-level element type in the document.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="70385-152">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="70385-152">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="70385-153">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="70385-153">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="70385-154">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="70385-154">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="70385-155">Creare il modello seguente (XPathAxesSampleC.xml) e salvarlo nella directory in cui:</span><span class="sxs-lookup"><span data-stu-id="70385-155">Create the following template (XPathAxesSampleC.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order[../@CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="70385-156">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-156">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="70385-157">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="70385-157">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="70385-158">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="70385-159">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="70385-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="70385-160">Di seguito viene indicato il set di risultati parziale dell'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="70385-160">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</Order>  
</ROOT>  
```  
  
### <a name="d-specify-the-attribute-axis"></a><span data-ttu-id="70385-161">D.</span><span class="sxs-lookup"><span data-stu-id="70385-161">D.</span></span> <span data-ttu-id="70385-162">Specificare l'asse attribute</span><span class="sxs-lookup"><span data-stu-id="70385-162">Specify the attribute axis</span></span>  
 <span data-ttu-id="70385-163">La query XPath seguente seleziona tutti gli **\<Customer>** elementi figlio del nodo di contesto il cui valore di attributo **CustomerID** è 1:</span><span class="sxs-lookup"><span data-stu-id="70385-163">The following XPath query selects all the **\<Customer>** child elements of the context node with a **CustomerID** attribute value of 1:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]  
```  
  
 <span data-ttu-id="70385-164">Nel predicato `attribute::CustomerID` `attribute` è l'asse e `CustomerID` è il test di nodo (se `CustomerID` è un attributo, il test del nodo è true, perché il nodo **\<attribute>** è il nodo primario per l' `attribute` asse).</span><span class="sxs-lookup"><span data-stu-id="70385-164">In the predicate `attribute::CustomerID`, `attribute` is the axis and `CustomerID` is the node test (if `CustomerID` is an attribute the node test is TRUE, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span>  
  
 <span data-ttu-id="70385-165">È possibile specificare un collegamento all'asse `attribute` (@) e, poiché l'asse `child` è l'asse predefinito, può essere omesso dalla query:</span><span class="sxs-lookup"><span data-stu-id="70385-165">A shortcut to the `attribute` axis (@) can be specified, and because `child` is the default axis, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="70385-166">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="70385-166">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="70385-167">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="70385-167">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="70385-168">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="70385-168">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="70385-169">Creare il modello seguente (XPathAxesSampleD.xml) e salvarlo nella directory in cui è stato salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="70385-169">Create the following template (XPathAxesSampleD.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        child::Customer[attribute::CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="70385-170">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-170">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="70385-171">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="70385-171">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="70385-172">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="70385-172">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="70385-173">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="70385-173">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="70385-174">Di seguito viene indicato il set di risultati parziale dell'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="70385-174">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280"   
            TerritoryID="1" AccountNumber="1"   
            CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
       <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
                    OrderQty="1" UnitPriceDiscount="0" />   
      ...   
    </Order>  
   ...  
  </Customer>  
</ROOT>  
```  
  
  
