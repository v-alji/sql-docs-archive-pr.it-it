---
title: Specifica di operatori booleani in query XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath operators [SQLXML]
- OR operator
- Boolean operators
- XPath queries [SQLXML], Boolean operators
- operators [SQLXML]
ms.assetid: 9928cff5-62ac-42aa-96bf-2e09a1df0bc3
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dd6e1f120b53382ce984684ea352b36d34b768
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623992"
---
# <a name="specifying-boolean-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="1b7ac-102">Specifica di operatori booleani in query XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1b7ac-102">Specifying Boolean Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="1b7ac-103">Negli esempi seguenti viene illustrato come specificare operatori booleani in query XPath.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-103">The following example shows how Boolean operators are specified in XPath queries.</span></span> <span data-ttu-id="1b7ac-104">Le query XPath di questi esempi vengono specificate sullo schema di mapping contenuto in SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="1b7ac-105">Per informazioni su questo schema di esempio, vedere [schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1b7ac-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1b7ac-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="1b7ac-106">Examples</span></span>  
  
### <a name="a-specify-the-or-boolean-operator"></a><span data-ttu-id="1b7ac-107">R.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-107">A.</span></span> <span data-ttu-id="1b7ac-108">Specificare l'operatore booleano OR</span><span class="sxs-lookup"><span data-stu-id="1b7ac-108">Specify the OR Boolean operator</span></span>  
 <span data-ttu-id="1b7ac-109">Questa query XPath restituisce gli **\<Customer>** elementi figlio del nodo di contesto il cui valore di attributo **CustomerID** è 13 o 31:</span><span class="sxs-lookup"><span data-stu-id="1b7ac-109">This XPath query returns the **\<Customer>** element children of the context node with the **CustomerID** attribute value of 13 or 31:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="13" or attribute::CustomerID="31"]  
```  
  
 <span data-ttu-id="1b7ac-110">È possibile specificare un collegamento all'asse `attribute` (@) e, poiché l'asse `child` è l'asse predefinito, può essere omesso dalla query:</span><span class="sxs-lookup"><span data-stu-id="1b7ac-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted:</span></span>  
  
```  
/Customer[@CustomerID="13" or @CustomerID="31"]  
```  
  
 <span data-ttu-id="1b7ac-111">Nel predicato `attribute` è l'asse e `CustomerID` è il test di nodo (true se **CustomerID** è un **\<attribute>** nodo, perché il nodo **\<attribute>** è il nodo primario per l' `attribute` asse).</span><span class="sxs-lookup"><span data-stu-id="1b7ac-111">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an **\<attribute>** node, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span> <span data-ttu-id="1b7ac-112">Il predicato filtra gli **\<Customer>** elementi e restituisce solo quelli che soddisfano la condizione specificata nel predicato.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-112">The predicate filters the **\<Customer>** elements and returns only those that satisfy the condition specified in the predicate.</span></span>  
  
##### <a name="to-test-the-xpath-queries-against-the-mapping-schema"></a><span data-ttu-id="1b7ac-113">Per testare query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="1b7ac-113">To test the XPath queries against the mapping schema</span></span>  
  
1.  <span data-ttu-id="1b7ac-114">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="1b7ac-115">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="1b7ac-116">Creare il modello seguente (BooleanOperatorsA.xml) e salvarlo nella directory in cui è stato salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-116">Create the following template (BooleanOperatorsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="13" or @CustomerID="31"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1b7ac-117">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1b7ac-118">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1b7ac-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="1b7ac-119">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="1b7ac-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1b7ac-120">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1b7ac-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1b7ac-121">Di seguito è riportato il set di risultati relativo all'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="1b7ac-121">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="31" SalesPersonID="286" TerritoryID="7" AccountNumber="31" CustomerType="S" Orders="Ord-51803 Ord-69427">  
    <Order SalesOrderID="Ord-51803" SalesPersonID="286" OrderDate="2003-08-01T00:00:00" DueDate="2003-08-13T00:00:00" ShipDate="2003-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-718" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-838" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    <Order SalesOrderID="Ord-69427" SalesPersonID="286" OrderDate="2004-05-01T00:00:00" DueDate="2004-05-13T00:00:00" ShipDate="2004-05-08T00:00:00">  
      <OrderDetail ProductID="Prod-835" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
  </Customer>  
</ROOT>  
```  
  
  
