---
title: Specifica di predicati di selezione nel percorso (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- predicates [SQLXML]
- position-based filtering [SQLXML]
- XPath queries [SQLXML], location paths
- filtering [SQLXML]
- location path for XPath query
ms.assetid: dbef4cf4-a89b-4d7e-b72b-4062f7b29a80
author: rothja
ms.author: jroth
ms.openlocfilehash: d323558556fb05d350e48ea9218a8e9b8dc9b5c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629287"
---
# <a name="specifying-selection-predicates-in-the-location-path-sqlxml-40"></a><span data-ttu-id="f76ae-102">Definizione di predicati di selezione nel percorso (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f76ae-102">Specifying Selection Predicates in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="f76ae-103">Un predicato filtra un set di nodi rispetto a un asse (simile a una clausola WHERE in un'istruzione SELECT).</span><span class="sxs-lookup"><span data-stu-id="f76ae-103">A predicate filters a node-set with respect to an axis (similar to a WHERE clause in a SELECT statement).</span></span> <span data-ttu-id="f76ae-104">Il predicato viene specificato tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="f76ae-104">The predicate is specified between brackets.</span></span> <span data-ttu-id="f76ae-105">Per filtrare ogni nodo nel set di nodi, l'espressione del predicato viene valutata con il nodo come nodo di contesto e con il numero di nodi nel set di nodi come dimensioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="f76ae-105">For each node in the node-set to be filtered, the predicate expression is evaluated with that node as the context node, with the number of nodes in the node-set as context size.</span></span> <span data-ttu-id="f76ae-106">Se l'espressione del predicato restituisce TRUE per il nodo, il nodo viene incluso nel set di nodi risultante.</span><span class="sxs-lookup"><span data-stu-id="f76ae-106">If the predicate expression evaluates to TRUE for that node, the node is included in the resulting node-set.</span></span>  
  
 <span data-ttu-id="f76ae-107">XPath consente inoltre l'applicazione di filtri basata sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f76ae-107">XPath also allows position-based filtering.</span></span> <span data-ttu-id="f76ae-108">Un'espressione del predicato valutata in numero seleziona il nodo dell'ordinale.</span><span class="sxs-lookup"><span data-stu-id="f76ae-108">A predicate expression evaluating to a number selects that ordinal node.</span></span> <span data-ttu-id="f76ae-109">Il percorso `Customer[3]`, ad esempio, restituisce il terzo cliente.</span><span class="sxs-lookup"><span data-stu-id="f76ae-109">For example, the location path `Customer[3]` returns the third customer.</span></span> <span data-ttu-id="f76ae-110">Predicati numerici di questo tipo non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="f76ae-110">Such numeric predicates are not supported.</span></span> <span data-ttu-id="f76ae-111">Sono supportate solo le espressioni del predicato che restituiscono un risultato booleano.</span><span class="sxs-lookup"><span data-stu-id="f76ae-111">Only predicate expressions that return a Boolean result are supported.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f76ae-112">Per informazioni sulle limitazioni di questa implementazione XPath di XPath e sulle differenze tra it e W3C Specification, vedere [Introduzione all'uso di query XPath &#40;SQLXML 4,0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f76ae-112">For information about the limitations of this XPath implementation of XPath and the differences between it and the W3C specification, see [Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span></span>  
  
## <a name="selection-predicate-example-1"></a><span data-ttu-id="f76ae-113">Predicato di selezione: esempio 1</span><span class="sxs-lookup"><span data-stu-id="f76ae-113">Selection Predicate: Example 1</span></span>  
 <span data-ttu-id="f76ae-114">L'espressione XPath seguente (percorso) Seleziona dal nodo di contesto corrente tutti gli **\<Customer>** elementi figlio che dispongono dell'attributo **CustomerID** con valore ALFKI:</span><span class="sxs-lookup"><span data-stu-id="f76ae-114">The following XPath expression (location path) selects from the current context node all the **\<Customer>** element children that have the **CustomerID** attribute with value of ALFKI:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="ALFKI"]  
```  
  
 <span data-ttu-id="f76ae-115">In questa query XPath `child` e `attribute` sono nomi di asse.</span><span class="sxs-lookup"><span data-stu-id="f76ae-115">In this XPath query, `child` and `attribute` are axis names.</span></span> <span data-ttu-id="f76ae-116">`Customer`è il test di nodo (TRUE se `Customer` è un oggetto **\<element node>** , perché **\<element>** è il tipo di nodo principale per l' `child` asse).</span><span class="sxs-lookup"><span data-stu-id="f76ae-116">`Customer` is the node test (TRUE if `Customer` is an **\<element node>**, because **\<element>** is the principal node type for the `child` axis).</span></span> <span data-ttu-id="f76ae-117">`attribute::CustomerID="ALFKI"` è il predicato.</span><span class="sxs-lookup"><span data-stu-id="f76ae-117">`attribute::CustomerID="ALFKI"` is the predicate.</span></span> <span data-ttu-id="f76ae-118">Nel predicato `attribute` è l'asse e `CustomerID` è il test di nodo (true se **CustomerID** è un attributo del nodo di contesto, perché **\<attribute>** è il tipo di nodo principale dell' `attribute` asse).</span><span class="sxs-lookup"><span data-stu-id="f76ae-118">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an attribute of the context node, because **\<attribute>** is the principal node type of `attribute` axis).</span></span>  
  
 <span data-ttu-id="f76ae-119">Utilizzando la sintassi abbreviata, la query XPath può essere specificata anche nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f76ae-119">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer[@CustomerID="ALFKI"]  
```  
  
## <a name="selection-predicate-example-2"></a><span data-ttu-id="f76ae-120">Predicato di selezione: esempio 2</span><span class="sxs-lookup"><span data-stu-id="f76ae-120">Selection Predicate: Example 2</span></span>  
 <span data-ttu-id="f76ae-121">L'espressione XPath seguente (percorso) Seleziona dal nodo di contesto corrente tutti i **\<Order>** nipoti con l'attributo **SalesOrderID** con valore 1:</span><span class="sxs-lookup"><span data-stu-id="f76ae-121">The following XPath expression (location path) selects from the current context node all the **\<Order>** grandchildren that have the **SalesOrderID** attribute with the value 1:</span></span>  
  
```  
/child::Customer/child::Order[attribute::SalesOrderID="1"]  
```  
  
 <span data-ttu-id="f76ae-122">In questa espressione XPath `child` e `attribute` sono nomi di asse.</span><span class="sxs-lookup"><span data-stu-id="f76ae-122">In this XPath expression, `child` and `attribute` are the axis names.</span></span> <span data-ttu-id="f76ae-123">`Customer`, `Order` e `SalesOrderID` sono i test di nodo.</span><span class="sxs-lookup"><span data-stu-id="f76ae-123">`Customer`, `Order`, and `SalesOrderID` are the node tests.</span></span> <span data-ttu-id="f76ae-124">`attribute::OrderID="1"` è il predicato.</span><span class="sxs-lookup"><span data-stu-id="f76ae-124">`attribute::OrderID="1"` is the predicate.</span></span>  
  
 <span data-ttu-id="f76ae-125">Utilizzando la sintassi abbreviata, la query XPath può essere specificata anche nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f76ae-125">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer/Order[@SalesOrderID="1"]  
```  
  
## <a name="selection-predicate-example-3"></a><span data-ttu-id="f76ae-126">Predicato di selezione: esempio 3</span><span class="sxs-lookup"><span data-stu-id="f76ae-126">Selection Predicate: Example 3</span></span>  
 <span data-ttu-id="f76ae-127">L'espressione XPath seguente (percorso) Seleziona dal nodo di contesto corrente tutti gli **\<Customer>** elementi figlio che hanno uno o più **\<ContactName>** elementi figlio:</span><span class="sxs-lookup"><span data-stu-id="f76ae-127">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children that have one or more **\<ContactName>** children:</span></span>  
  
```  
child::Customer[child::ContactName]  
```  
  
 <span data-ttu-id="f76ae-128">In questo esempio si presuppone che **\<ContactName>** sia un elemento figlio dell' **\<Customer>** elemento nel documento XML, denominato *mapping incentrato sugli elementi* in uno schema XSD con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="f76ae-128">This example assumes that the **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, which is referred to as *element-centric mapping* in an annotated XSD schema.</span></span>  
  
 <span data-ttu-id="f76ae-129">In questa espressione XPath `child` è il nome dell'asse.</span><span class="sxs-lookup"><span data-stu-id="f76ae-129">In this XPath expression, `child` is the axis name.</span></span> <span data-ttu-id="f76ae-130">`Customer`è il test di nodo (TRUE se `Customer` è un **\<element>** nodo, perché **\<element>** è il tipo di nodo principale per l' `child` asse).</span><span class="sxs-lookup"><span data-stu-id="f76ae-130">`Customer` is the node test (TRUE if `Customer` is an **\<element>** node, because **\<element>** is the principal node type for `child` axis).</span></span> <span data-ttu-id="f76ae-131">`child::ContactName` è il predicato.</span><span class="sxs-lookup"><span data-stu-id="f76ae-131">`child::ContactName` is the predicate.</span></span> <span data-ttu-id="f76ae-132">Nel predicato `child` è l'asse e `ContactName` è il test di nodo (true se `ContactName` è un **\<element>** nodo).</span><span class="sxs-lookup"><span data-stu-id="f76ae-132">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an **\<element>** node).</span></span>  
  
 <span data-ttu-id="f76ae-133">Questa espressione restituisce solo gli **\<Customer>** elementi figlio del nodo di contesto che hanno **\<ContactName>** elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="f76ae-133">This expression returns only the **\<Customer>** element children of the context node that have **\<ContactName>** element children.</span></span>  
  
 <span data-ttu-id="f76ae-134">Utilizzando la sintassi abbreviata, la query XPath può essere specificata anche nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f76ae-134">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[ContactName]  
```  
  
## <a name="selection-predicate-example-4"></a><span data-ttu-id="f76ae-135">Predicato di selezione: esempio 4</span><span class="sxs-lookup"><span data-stu-id="f76ae-135">Selection Predicate: Example 4</span></span>  
 <span data-ttu-id="f76ae-136">L'espressione XPath seguente seleziona gli **\<Customer>** elementi figlio del nodo di contesto che non dispongono di **\<ContactName>** elementi figlio:</span><span class="sxs-lookup"><span data-stu-id="f76ae-136">The following XPath expression selects **\<Customer>** element children of the context node that do not have **\<ContactName>** element children:</span></span>  
  
```  
child::Customer[not(child::ContactName)]  
```  
  
 <span data-ttu-id="f76ae-137">In questo esempio si presuppone che **\<ContactName>** sia un elemento figlio dell' **\<Customer>** elemento nel documento XML e che il campo ContactName non sia necessario nel database.</span><span class="sxs-lookup"><span data-stu-id="f76ae-137">This example assumes that **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, and the ContactName field is not required in the database.</span></span>  
  
 <span data-ttu-id="f76ae-138">In questo esempio, `child` è l'asse.</span><span class="sxs-lookup"><span data-stu-id="f76ae-138">In this example, `child` is the axis.</span></span> <span data-ttu-id="f76ae-139">`Customer`è il test di nodo (TRUE se `Customer` è un \<element> nodo).</span><span class="sxs-lookup"><span data-stu-id="f76ae-139">`Customer` is the node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="f76ae-140">`not(child::ContactName)` è il predicato.</span><span class="sxs-lookup"><span data-stu-id="f76ae-140">`not(child::ContactName)` is the predicate.</span></span> <span data-ttu-id="f76ae-141">Nel predicato `child` è l'asse e `ContactName` è il test di nodo (true se `ContactName` è un \<element> nodo).</span><span class="sxs-lookup"><span data-stu-id="f76ae-141">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an \<element> node).</span></span>  
  
 <span data-ttu-id="f76ae-142">Utilizzando la sintassi abbreviata, la query XPath può essere specificata anche nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f76ae-142">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[not(ContactName)]  
```  
  
## <a name="selection-predicate-example-5"></a><span data-ttu-id="f76ae-143">Predicato di selezione: esempio 5</span><span class="sxs-lookup"><span data-stu-id="f76ae-143">Selection Predicate: Example 5</span></span>  
 <span data-ttu-id="f76ae-144">L'espressione XPath seguente seleziona dal nodo di contesto corrente tutti gli **\<Customer>** elementi figlio che dispongono dell'attributo **CustomerID** :</span><span class="sxs-lookup"><span data-stu-id="f76ae-144">The following XPath expression selects from the current context node all the **\<Customer>** children that have the **CustomerID** attribute:</span></span>  
  
```  
child::Customer[attribute::CustomerID]  
```  
  
 <span data-ttu-id="f76ae-145">In questo esempio `child` è l'asse e `Customer` è il test di nodo (true se `Customer` è un \<element> nodo).</span><span class="sxs-lookup"><span data-stu-id="f76ae-145">In this example, `child` is the axis and `Customer` is node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="f76ae-146">`attribute::CustomerID` è il predicato.</span><span class="sxs-lookup"><span data-stu-id="f76ae-146">`attribute::CustomerID` is the predicate.</span></span> <span data-ttu-id="f76ae-147">Nel predicato, `attribute` è l'asse e `CustomerID` è il predicato (true se `CustomerID` è un **\<attribute>** nodo).</span><span class="sxs-lookup"><span data-stu-id="f76ae-147">In the predicate, `attribute` is the axis and `CustomerID` is the predicate (TRUE if `CustomerID` is an **\<attribute>** node).</span></span>  
  
 <span data-ttu-id="f76ae-148">Utilizzando la sintassi abbreviata, la query XPath può essere specificata anche nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f76ae-148">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[@CustomerID]  
```  
  
## <a name="selection-predicate-example-6"></a><span data-ttu-id="f76ae-149">Predicato di selezione: esempio 6</span><span class="sxs-lookup"><span data-stu-id="f76ae-149">Selection Predicate: Example 6</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="f76ae-150">SQLXML 4.0 include il supporto per query XPath che contengono un prodotto incrociato nel predicato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f76ae-150">SQLXML 4.0 includes support for XPath queries that contain a cross-product in the predicate, as shown in the following example:</span></span>  
  
```  
Customer[Order/@OrderDate=Order/@ShipDate]  
```  
  
 <span data-ttu-id="f76ae-151">La query seleziona tutti i clienti con un elemento `Order` per cui `OrderDate` è uguale a `ShipDate` di qualsiasi `Order`.</span><span class="sxs-lookup"><span data-stu-id="f76ae-151">This query selects all customers with any `Order` for which the `OrderDate` equals the `ShipDate` of any `Order`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f76ae-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f76ae-152">See Also</span></span>  
 <span data-ttu-id="f76ae-153">[Introduzione agli schemi XSD con annotazioni &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="f76ae-153">[Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="f76ae-154">Formattazione XML sul lato client &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f76ae-154">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
