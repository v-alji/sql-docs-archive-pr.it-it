---
title: Specifica di operatori relazionali nelle query XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], relational operators
- relational operators [SQLXML]
- XPath operators [SQLXML]
- operators [SQLXML]
ms.assetid: 177a0eb2-11ef-4459-a317-485a433ee769
author: rothja
ms.author: jroth
ms.openlocfilehash: 50d59ebd3a776386c61f4c3a8a1e892d30981d1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623984"
---
# <a name="specifying-relational-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="666cd-102">Specifica di operatori relazionali nelle query XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="666cd-102">Specifying Relational Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="666cd-103">Negli esempi seguenti viene illustrato come specificare gli operatori relazionali nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="666cd-103">The following examples show how relational operators are specified in XPath queries.</span></span> <span data-ttu-id="666cd-104">Le query XPath di questi esempi vengono specificate sullo schema di mapping contenuto in SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="666cd-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="666cd-105">Per informazioni su questo schema di esempio, vedere [schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="666cd-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="666cd-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="666cd-106">Examples</span></span>  
  
### <a name="a-specify-relational-operator"></a><span data-ttu-id="666cd-107">R.</span><span class="sxs-lookup"><span data-stu-id="666cd-107">A.</span></span> <span data-ttu-id="666cd-108">Specificare un operatore relazionale</span><span class="sxs-lookup"><span data-stu-id="666cd-108">Specify relational operator</span></span>  
 <span data-ttu-id="666cd-109">Questa query XPath restituisce gli elementi figlio dell' **\<Customer>** elemento in cui il valore dell'attributo **CustomerID** è "1" e dove gli elementi figlio contengono un elemento **\<Order>** **\<OrderDetail>** figlio con un attributo **OrderQty** con un valore maggiore di 3:</span><span class="sxs-lookup"><span data-stu-id="666cd-109">This XPath query returns the child elements of the **\<Customer>** element where the **CustomerID** attribute value is "1" and where any child **\<Order>** elements contain an **\<OrderDetail>** child with a **OrderQty** attribute with a value greater than 3:</span></span>  
  
```  
/child::Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
 <span data-ttu-id="666cd-110">Il predicato specificato tra parentesi quadre filtra gli **\<Customer>** elementi.</span><span class="sxs-lookup"><span data-stu-id="666cd-110">The predicate specified in the brackets filters the **\<Customer>** elements.</span></span> <span data-ttu-id="666cd-111">**\<Customer>** Vengono restituiti solo gli elementi con almeno un **\<OrderDetail>** nipote con un valore di attributo OrderQty maggiore di 3.</span><span class="sxs-lookup"><span data-stu-id="666cd-111">Only the **\<Customer>** elements that have at least one **\<OrderDetail>** grandchild with a OrderQty attribute value greater than 3 are returned.</span></span>  
  
 <span data-ttu-id="666cd-112">L'asse `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="666cd-112">The `child` axis is the default.</span></span> <span data-ttu-id="666cd-113">È pertanto possibile specificare la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="666cd-113">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="666cd-114">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="666cd-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="666cd-115">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="666cd-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="666cd-116">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="666cd-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="666cd-117">Creare il modello SpecifyRelationalA.xml seguente e salvarlo nella directory in cui viene salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="666cd-117">Create the following template (SpecifyRelationalA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="666cd-118">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="666cd-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="666cd-119">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="666cd-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="666cd-120">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="666cd-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="666cd-121">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="666cd-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="666cd-122">Di seguito è riportato il set di risultati relativo all'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="666cd-122">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-760" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-766" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-757" UnitPrice="1049.7528" OrderQty="4" UnitPriceDiscount="0" />   
</ROOT>  
```  
  
### <a name="b-specify-relational-operator-in-the-xpath-query-and-use-boolean-function-to-compare-the-result"></a><span data-ttu-id="666cd-123">B.</span><span class="sxs-lookup"><span data-stu-id="666cd-123">B.</span></span> <span data-ttu-id="666cd-124">Specificare un operatore relazionale nella query XPath e utilizzare una funzione booleana per confrontare il risultato</span><span class="sxs-lookup"><span data-stu-id="666cd-124">Specify relational operator in the XPath query and use Boolean function to compare the result</span></span>  
 <span data-ttu-id="666cd-125">Questa query restituisce tutti gli **\<Order>** elementi figlio del nodo di contesto con un valore dell'attributo **SalesPersonID** inferiore a 270:</span><span class="sxs-lookup"><span data-stu-id="666cd-125">This query returns all the **\<Order>** element children of the context node that have an **SalesPersonID** attribute value that is less than 270:</span></span>  
  
```  
/child::Customer/child::Order[(attribute::SalesPersonID < 270)=true()]  
```  
  
 <span data-ttu-id="666cd-126">È possibile specificare un collegamento all'asse `attribute` (@) e, poiché l'asse `child` è l'asse predefinito, può essere omesso dalla query:</span><span class="sxs-lookup"><span data-stu-id="666cd-126">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer/Order[(@SalesPersonID < 270)=true()]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="666cd-127">Quando questa query viene specificata in un modello, il carattere di < deve essere codificato come entità perché il carattere < ha un significato speciale in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="666cd-127">When this query is specified in a template, the < character must be entity encoded because the < character has special meaning in an XML document.</span></span> <span data-ttu-id="666cd-128">In un modello usare `<` per specificare il carattere <.</span><span class="sxs-lookup"><span data-stu-id="666cd-128">In a template, use `<` to specify the < character.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="666cd-129">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="666cd-129">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="666cd-130">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="666cd-130">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="666cd-131">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="666cd-131">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="666cd-132">Creare il modello SpecifyRelationalB.xml seguente e salvarlo nella directory in cui viene salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="666cd-132">Create the following template (SpecifyRelationalB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="SampleSchema1.xml">  
            /Customer/Order[(@SalesPersonID<270)=true()]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="666cd-133">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="666cd-133">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="666cd-134">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="666cd-134">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="666cd-135">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="666cd-135">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="666cd-136">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="666cd-136">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="666cd-137">Di seguito viene indicato il set di risultati parziale dell'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="666cd-137">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-46613" SalesPersonID="268"   
         OrderDate="2002-07-01T00:00:00"   
         DueDate="2002-07-13T00:00:00"   
         ShipDate="2002-07-08T00:00:00">  
    <OrderDetail ProductID="Prod-739" UnitPrice="917.9363"   
                 OrderQty="2" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-779" UnitPrice="1491.4221"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-825" UnitPrice="242.1391"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  <Order SalesOrderID="Ord-71919" SalesPersonID="268"  
         OrderDate="2004-06-01T00:00:00"   
         DueDate="2004-06-13T00:00:00"   
         ShipDate="2004-06-08T00:00:00">  
    <OrderDetail ProductID="Prod-961" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-965" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-966" UnitPrice="1716.5304"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  ...  
</ROOT>  
```  
  
  
