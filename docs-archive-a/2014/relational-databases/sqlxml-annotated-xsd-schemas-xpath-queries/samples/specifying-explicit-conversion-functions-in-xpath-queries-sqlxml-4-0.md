---
title: Specifica di funzioni di conversione esplicita nelle query XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit conversion functions [SQLXML]
- string function
- number function
- XPath queries [SQLXML], explicit conversion functions
ms.assetid: 1111cb5d-2bd9-4bdb-8de2-dc0e47452dd6
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b4b9bd5f5665c8cb86cb74c1397e2bd06e113fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623988"
---
# <a name="specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="72d85-102">Specifica di funzioni di conversione esplicita in query XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="72d85-102">Specifying Explicit Conversion Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="72d85-103">Negli esempi seguenti viene illustrato come specificare le funzioni di conversione esplicita nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="72d85-103">The following examples show how explicit conversion functions are specified in XPath queries.</span></span> <span data-ttu-id="72d85-104">Le query XPath di questi esempi vengono specificate sullo schema di mapping contenuto in SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="72d85-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="72d85-105">Per informazioni su questo schema di esempio, vedere [schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="72d85-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="72d85-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="72d85-106">Examples</span></span>  
  
### <a name="a-use-the-number-explicit-conversion-function"></a><span data-ttu-id="72d85-107">R.</span><span class="sxs-lookup"><span data-stu-id="72d85-107">A.</span></span> <span data-ttu-id="72d85-108">Utilizzo della funzione di conversione esplicita number ()</span><span class="sxs-lookup"><span data-stu-id="72d85-108">Use the number() explicit conversion function</span></span>  
 <span data-ttu-id="72d85-109">La funzione `number()` converte un argomento in un numero.</span><span class="sxs-lookup"><span data-stu-id="72d85-109">The `number()` function converts an argument to a number.</span></span>  
  
 <span data-ttu-id="72d85-110">Supponendo che il valore di **ContactID** sia non numerico, la query seguente converte **ContactID** in un numero e lo confronta con il valore 4.</span><span class="sxs-lookup"><span data-stu-id="72d85-110">Assuming the value of **ContactID** is nonnumeric, the following query converts **ContactID** to a number and compares it with the value 4.</span></span> <span data-ttu-id="72d85-111">La query restituisce quindi tutti gli **\<Employee>** elementi figlio del nodo di contesto con l'attributo **ContactID** con valore numerico 4:</span><span class="sxs-lookup"><span data-stu-id="72d85-111">The query then returns all **\<Employee>** element children of the context node with the **ContactID** attribute that has a numeric value of 4:</span></span>  
  
```  
/child::Contact[number(attribute::ContactID)= 4]  
```  
  
 <span data-ttu-id="72d85-112">È possibile specificare un collegamento all'asse `attribute` (@) e, poiché l'asse `child` è l'asse predefinito, può essere omesso dalla query:</span><span class="sxs-lookup"><span data-stu-id="72d85-112">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[number(@ContactID) = 4]  
```  
  
 <span data-ttu-id="72d85-113">In termini relazionali, la query restituisce un dipendente con **ContactID** 4.</span><span class="sxs-lookup"><span data-stu-id="72d85-113">In relational terms, the query returns an employee with a **ContactID** of 4.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="72d85-114">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="72d85-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="72d85-115">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="72d85-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="72d85-116">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="72d85-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="72d85-117">Creare il modello seguente (ExplicitConversionA.xml) e salvarlo nella directory in cui è stato salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="72d85-117">Create the following template (ExplicitConversionA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact[number(@ContactID)=4]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="72d85-118">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="72d85-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="72d85-119">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="72d85-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="72d85-120">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="72d85-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="72d85-121">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="72d85-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="72d85-122">Di seguito è riportato il set di risultati relativo all'esecuzione di questo modello:</span><span class="sxs-lookup"><span data-stu-id="72d85-122">The result set for this template execution is:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
### <a name="b-use-the-string-explicit-conversion-function"></a><span data-ttu-id="72d85-123">B.</span><span class="sxs-lookup"><span data-stu-id="72d85-123">B.</span></span> <span data-ttu-id="72d85-124">Utilizzo della funzione di conversione esplicita string ()</span><span class="sxs-lookup"><span data-stu-id="72d85-124">Use the string() explicit conversion function</span></span>  
 <span data-ttu-id="72d85-125">La funzione `string()` converte un argomento in una stringa.</span><span class="sxs-lookup"><span data-stu-id="72d85-125">The `string()` function converts an argument to a string.</span></span>  
  
 <span data-ttu-id="72d85-126">La query seguente converte **ContactID** in una stringa e la confronta con il valore di stringa "4".</span><span class="sxs-lookup"><span data-stu-id="72d85-126">The following query converts **ContactID** to a string and compares it with the string value "4".</span></span> <span data-ttu-id="72d85-127">La query restituisce tutti gli **\<Employee>** elementi figlio del nodo di contesto con un **ContactID** con un valore stringa "4":</span><span class="sxs-lookup"><span data-stu-id="72d85-127">The query returns all **\<Employee>** element children of the context node with a **ContactID** with a string value of "4":</span></span>  
  
```  
/child::Contact[string(attribute::ContactID)="4"]  
```  
  
 <span data-ttu-id="72d85-128">È possibile specificare un collegamento all'asse `attribute` (@) e, poiché l'asse `child` è l'asse predefinito, può essere omesso dalla query:</span><span class="sxs-lookup"><span data-stu-id="72d85-128">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[string(@ContactID)="4"]  
```  
  
 <span data-ttu-id="72d85-129">Dal punto di vista funzionale questa query restituisce gli stessi risultati della query di esempio precedente, sebbene la valutazione venga fatta rispetto a un valore stringa e non al valore numerico (ovvero il numero 4).</span><span class="sxs-lookup"><span data-stu-id="72d85-129">Functionally, this query returns the same results as the previous example query, though the evaluation is done against a string value and not the numeric value (that is, the number 4).</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="72d85-130">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="72d85-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="72d85-131">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="72d85-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="72d85-132">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="72d85-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="72d85-133">Creare il modello seguente (ExplicitConversionB.xml) e salvarlo nella directory in cui è stato salvato il file SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="72d85-133">Create the following template (ExplicitConversionB.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Contact[string(@ContactID)="4"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="72d85-134">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="72d85-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="72d85-135">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="72d85-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="72d85-136">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="72d85-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="72d85-137">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="72d85-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="72d85-138">Di seguito è riportato il set di risultati relativo all'esecuzione del modello:</span><span class="sxs-lookup"><span data-stu-id="72d85-138">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
  
