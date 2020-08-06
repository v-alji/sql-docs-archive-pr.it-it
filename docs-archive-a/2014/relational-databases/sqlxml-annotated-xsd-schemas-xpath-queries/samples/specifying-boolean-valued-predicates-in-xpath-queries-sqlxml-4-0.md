---
title: Specifica di predicati con valori booleani nelle query XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- nested predicates
- successive predicates
- predicates [SQLXML]
- top-level predicates
- Boolean-valued predicates
- multiple predicates
ms.assetid: 5f6e7219-6911-4bca-a54b-56b95e0b43dd
author: rothja
ms.author: jroth
ms.openlocfilehash: 56f2f94ec895c5b76382d5103ca9d518b78cc899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623991"
---
# <a name="specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="a1a08-102">Specifica di predicati con valori booleani nelle query XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a1a08-102">Specifying Boolean-Valued Predicates in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="a1a08-103">Negli esempi seguenti viene illustrato come specificare predicati con valori booleani nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="a1a08-103">The following examples show how Boolean-valued predicates are specified in XPath queries.</span></span> <span data-ttu-id="a1a08-104">Le query XPath di questi esempi vengono specificate sullo schema di mapping contenuto in SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="a1a08-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="a1a08-105">Per informazioni su questo schema di esempio, vedere [schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="a1a08-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a1a08-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="a1a08-106">Examples</span></span>  
  
### <a name="a-specify-multiple-predicates"></a><span data-ttu-id="a1a08-107">R.</span><span class="sxs-lookup"><span data-stu-id="a1a08-107">A.</span></span> <span data-ttu-id="a1a08-108">Specificare più predicati</span><span class="sxs-lookup"><span data-stu-id="a1a08-108">Specify multiple predicates</span></span>  
 <span data-ttu-id="a1a08-109">Nella query XPath seguente vengono utilizzati più predicati per trovare informazioni sull'ordine per un ID ordine e un ID cliente specifici:</span><span class="sxs-lookup"><span data-stu-id="a1a08-109">The following XPath query uses multiple predicates to find order information for a given order ID and a customer ID:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]/child::Order[attribute::OrderID="Ord-43860"]  
```  
  
 <span data-ttu-id="a1a08-110">È possibile specificare un collegamento all'asse `attribute` (@) e, poiché l'asse `child` è l'asse predefinito, può essere omesso dalla query:</span><span class="sxs-lookup"><span data-stu-id="a1a08-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="a1a08-111">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="a1a08-111">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="a1a08-112">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="a1a08-112">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="a1a08-113">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="a1a08-113">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="a1a08-114">Creare il modello BooleanValuedPredicatesA.xml seguente e salvarlo nella directory in cui viene salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="a1a08-114">Create the following template (BooleanValuedPredicatesA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="a1a08-115">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="a1a08-115">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="a1a08-116">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1a08-116">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="a1a08-117">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="a1a08-117">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a1a08-118">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a1a08-118">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
     <span data-ttu-id="a1a08-119">Il risultato è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a1a08-119">Here is the result:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
        <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-761" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-762" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-765" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-768" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-770" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
      </Order>  
    </ROOT>  
    ```  
  
### <a name="b-specify-successive-and-nested-predicates"></a><span data-ttu-id="a1a08-120">B.</span><span class="sxs-lookup"><span data-stu-id="a1a08-120">B.</span></span> <span data-ttu-id="a1a08-121">Specificare predicati successivi e nidificati</span><span class="sxs-lookup"><span data-stu-id="a1a08-121">Specify successive and nested predicates</span></span>  
 <span data-ttu-id="a1a08-122">Nella query seguente viene illustrato l'utilizzo di predicati successivi.</span><span class="sxs-lookup"><span data-stu-id="a1a08-122">The following query shows using successive predicates.</span></span> <span data-ttu-id="a1a08-123">La query restituisce tutti gli **\<Customer>** elementi figlio del nodo di contesto con un attributo **SalesPersonID** con un valore 277 e un attributo **TerritoryID** con un valore pari a 3:</span><span class="sxs-lookup"><span data-stu-id="a1a08-123">The query returns all the **\<Customer>** child elements of the context node that have both a **SalesPersonID** attribute with a value of 277 and a **TerritoryID** attribute with a value of 3:</span></span>  
  
```  
/child::Customer[attribute::SalesPersonID="277"][attribute::TerritoryID="3"]  
```  
  
 <span data-ttu-id="a1a08-124">La query restituisce gli **\<Customer>** elementi che soddisfano entrambe le condizioni specificate nei predicati.</span><span class="sxs-lookup"><span data-stu-id="a1a08-124">The query returns the **\<Customer>** elements that satisfy both the conditions specified in the predicates.</span></span>  
  
 <span data-ttu-id="a1a08-125">È possibile specificare un collegamento all'asse `attribute` (@) e, poiché l'asse `child` è l'asse predefinito, può essere omesso dalla query:</span><span class="sxs-lookup"><span data-stu-id="a1a08-125">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@SalesPersonID="277"][@TerritoryID="3"]  
```  
  
 <span data-ttu-id="a1a08-126">Nella query XPath seguente viene illustrato l'utilizzo di predicati nidificati.</span><span class="sxs-lookup"><span data-stu-id="a1a08-126">The following XPath query illustrates the use of nested predicates.</span></span> <span data-ttu-id="a1a08-127">La query restituisce tutti gli **\<Customer>** elementi figlio del nodo di contesto che includono **\<Order>** elementi figlio con almeno un **\<Order>** elemento con un valore di attributo **SalesPersonID** pari a 2.</span><span class="sxs-lookup"><span data-stu-id="a1a08-127">The query returns all the **\<Customer>** child elements of the context node that include **\<Order>** child elements with at least one **\<Order>** element that has a **SalesPersonID** attribute value of 2.</span></span>  
  
```  
/Customer[Order[@SalesPersonID=2]]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="a1a08-128">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="a1a08-128">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="a1a08-129">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="a1a08-129">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="a1a08-130">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="a1a08-130">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="a1a08-131">Creare il modello nestedSuccessive.xml seguente e salvarlo nella directory in cui viene salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="a1a08-131">Create the following template (nestedSuccessive.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
             /Customer[@SalesPersonID="277"][@TerritoryID="3"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="a1a08-132">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="a1a08-132">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="a1a08-133">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1a08-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="a1a08-134">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="a1a08-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a1a08-135">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a1a08-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a1a08-136">Di seguito è riportato un risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="a1a08-136">The following is a partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="22" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="22" CustomerType="S"   
            Orders="Ord-43874 Ord-44519 Ord-46989 Ord-48013 Ord-49130 Ord-50274 Ord-51807 Ord-57113 Ord-63162 Ord-69495">  
    <Order SalesOrderID="Ord-43874" SalesPersonID="277"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
                   OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    ...  
  </Customer>  
  <Customer CustomerID="39" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="39" CustomerType="S"   
            Orders="Ord-47428 Ord-48367 Ord-49529 Ord-50742 Ord-53591 Ord-59051 Ord-65301 Ord-71912">    <Order SalesOrderID="Ord-47428" SalesPersonID="277"   
           OrderDate="2002-09-01T00:00:00"   
           DueDate="2002-09-13T00:00:00"   
           ShipDate="2002-09-08T00:00:00">  
      <OrderDetail ProductID="Prod-759" UnitPrice="563.7528" OrderQty="2" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-769" UnitPrice="563.7528" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
### <a name="c-specify-a-top-level-predicate"></a><span data-ttu-id="a1a08-137">C.</span><span class="sxs-lookup"><span data-stu-id="a1a08-137">C.</span></span> <span data-ttu-id="a1a08-138">Specificare un predicato di livello superiore</span><span class="sxs-lookup"><span data-stu-id="a1a08-138">Specify a top-level predicate</span></span>  
 <span data-ttu-id="a1a08-139">La query seguente restituisce i **\<Customer>** nodi elemento figlio del nodo di contesto che includono **\<Order>** elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="a1a08-139">The following query returns the **\<Customer>** child element nodes of the context node that have **\<Order>** element children.</span></span> <span data-ttu-id="a1a08-140">La query testa il percorso come predicato di livello superiore:</span><span class="sxs-lookup"><span data-stu-id="a1a08-140">The query tests the location path as the top-level predicate:</span></span>  
  
```  
/child::Customer[child::Order]  
```  
  
 <span data-ttu-id="a1a08-141">L'asse `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="a1a08-141">The `child` axis is the default.</span></span> <span data-ttu-id="a1a08-142">È pertanto possibile specificare la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a1a08-142">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="a1a08-143">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="a1a08-143">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="a1a08-144">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="a1a08-144">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="a1a08-145">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="a1a08-145">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="a1a08-146">Creare il modello TopLevelPredicate.xml seguente e salvarlo nella directory in cui viene salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="a1a08-146">Create the following template (TopLevelPredicate.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="a1a08-147">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="a1a08-147">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="a1a08-148">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1a08-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="a1a08-149">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="a1a08-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a1a08-150">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a1a08-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a1a08-151">Di seguito è riportato il risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="a1a08-151">Here is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280" TerritoryID="1" AccountNumber="1" CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    <Order SalesOrderID="Ord-44501" SalesPersonID="280" OrderDate="2001-11-01T00:00:00" DueDate="2001-11-13T00:00:00" ShipDate="2001-11-08T00:00:00">  
      <OrderDetail ProductID="Prod-725" UnitPrice="226.8571" OrderQty="3" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-726" UnitPrice="226.8571" OrderQty="2" UnitPriceDiscount="0" />   
      ...  
    </Order>    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
  
