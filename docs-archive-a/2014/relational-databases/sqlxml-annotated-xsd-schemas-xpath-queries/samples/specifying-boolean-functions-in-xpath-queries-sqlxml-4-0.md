---
title: Specifica di funzioni booleane in query XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], Boolean functions
- false function
- not function [SQLXML]
- true function
- Boolean functions
ms.assetid: c72cd333-9294-4d41-84f2-1748bf20e3eb
author: rothja
ms.author: jroth
ms.openlocfilehash: d230c7cd8792066732085b9ce501c0794687d17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623993"
---
# <a name="specifying-boolean-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="466fb-102">Definizione di funzioni booleane in query XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="466fb-102">Specifying Boolean Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="466fb-103">Negli esempi seguenti viene illustrato come specificare funzioni booleane in query XPath.</span><span class="sxs-lookup"><span data-stu-id="466fb-103">The following examples show how Boolean functions are specified in XPath queries.</span></span> <span data-ttu-id="466fb-104">Le query XPath di questi esempi vengono specificate sullo schema di mapping contenuto in SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="466fb-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="466fb-105">Per informazioni su questo schema di esempio, vedere [schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="466fb-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="466fb-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="466fb-106">Examples</span></span>  
  
## <a name="a-specify-the-not-boolean-function"></a><span data-ttu-id="466fb-107">R.</span><span class="sxs-lookup"><span data-stu-id="466fb-107">A.</span></span> <span data-ttu-id="466fb-108">Definizione della funzione booleana not()</span><span class="sxs-lookup"><span data-stu-id="466fb-108">Specify the not() Boolean function</span></span>  
 <span data-ttu-id="466fb-109">Questa query restituisce tutti gli **\<Customer>** elementi figlio del nodo di contesto che non dispongono di **\<Order>** elementi figlio:</span><span class="sxs-lookup"><span data-stu-id="466fb-109">This query returns all the **\<Customer>** child elements of the context node that do not have **\<Order>** child elements:</span></span>  
  
```  
/child::Customer[not(child::Order)]  
```  
  
 <span data-ttu-id="466fb-110">L'asse `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="466fb-110">The `child` axis is the default.</span></span> <span data-ttu-id="466fb-111">È pertanto possibile specificare la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="466fb-111">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="466fb-112">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="466fb-112">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="466fb-113">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="466fb-113">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="466fb-114">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="466fb-114">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="466fb-115">Creare il modello seguente (BooleanFunctionsA.xml) e salvarlo nella directory in cui è stato salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="466fb-115">Create the following template (BooleanFunctionsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[not(Order)]  
    </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="466fb-116">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="466fb-116">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="466fb-117">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="466fb-117">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="466fb-118">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="466fb-118">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="466fb-119">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="466fb-119">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="466fb-120">Di seguito viene indicato il set di risultati parziale dell'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="466fb-120">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
## <a name="b-specify-the-true-and-false-boolean-functions"></a><span data-ttu-id="466fb-121">B.</span><span class="sxs-lookup"><span data-stu-id="466fb-121">B.</span></span> <span data-ttu-id="466fb-122">Definizione delle funzioni booleane true() e false()</span><span class="sxs-lookup"><span data-stu-id="466fb-122">Specify the true() and false() Boolean functions</span></span>  
 <span data-ttu-id="466fb-123">Questa query restituisce tutti gli elementi **\<Customer>** figlio del nodo di contesto che non dispongono di **\<Order>** elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="466fb-123">This query returns all **\<Customer>** element children of the context node that do not have **\<Order>** child elements.</span></span> <span data-ttu-id="466fb-124">In termini relazionali, questa query restituisce tutti i clienti che non hanno effettuato ordini.</span><span class="sxs-lookup"><span data-stu-id="466fb-124">In relational terms, this query returns all customers who have not placed any orders.</span></span>  
  
```  
/child::Customer[child::Order=false()]  
```  
  
 <span data-ttu-id="466fb-125">L'asse `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="466fb-125">The `child` axis is the default.</span></span> <span data-ttu-id="466fb-126">È pertanto possibile specificare la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="466fb-126">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order=false()]  
```  
  
 <span data-ttu-id="466fb-127">La query equivale a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="466fb-127">This query is equivalent to the following:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
 <span data-ttu-id="466fb-128">Nella query seguente vengono restituiti tutti i clienti che hanno effettuato almeno un ordine:</span><span class="sxs-lookup"><span data-stu-id="466fb-128">The following query returns all the customers who have placed at least one order:</span></span>  
  
```  
/Customer[Order=true()]  
```  
  
 <span data-ttu-id="466fb-129">La query equivale a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="466fb-129">This query is equivalent to this one:</span></span>  
  
```  
/Customer[Order]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="466fb-130">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="466fb-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="466fb-131">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="466fb-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="466fb-132">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="466fb-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="466fb-133">Creare il modello seguente (BooleanFunctionsB.xml) e salvarlo nella directory in cui è stato salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="466fb-133">Create the following template (BooleanFunctionsB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order=false()]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="466fb-134">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="466fb-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="466fb-135">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="466fb-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="466fb-136">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="466fb-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="466fb-137">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="466fb-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="466fb-138">Di seguito viene indicato il set di risultati parziale dell'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="466fb-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
  
