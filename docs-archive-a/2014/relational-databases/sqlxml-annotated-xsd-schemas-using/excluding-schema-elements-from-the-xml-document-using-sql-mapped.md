---
title: 'Esclusione di elementi dello schema dal documento XML risultante tramite SQL: mapping (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- annotated XSD schemas, excluding schema elements
- mapped annotation
- table mapping [SQLXML], excluding schema elements
- sql:mapped
- excluding schema elements
- element mapping [SQLXML], excluding schema elements
- column mapping [SQLXML]
- XSD schemas [SQLXML], excluding schema elements
- attribute mapping [SQLXML], excluding schema elements
- table/view mapping [SQLXML], excluding schema elements
ms.assetid: 7d2649dd-0038-4a2c-b16d-f80f7c306966
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c79ae005b9630fcbfcd16bfc22c2aeb21b7bf9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628607"
---
# <a name="excluding-schema-elements-from-the-resulting-xml-document-using-sqlmapped-sqlxml-40"></a><span data-ttu-id="56bc7-102">Esclusione di elementi dello schema dal documento XML risultante tramite sql:mapped (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="56bc7-102">Excluding Schema Elements from the Resulting XML Document Using sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="56bc7-103">A causa del mapping predefinito, viene eseguito il mapping di ogni elemento e attributo nello schema XSD a una vista/tabella e a una colonna di database.</span><span class="sxs-lookup"><span data-stu-id="56bc7-103">Every element and attribute in the XSD schema maps to a database table/view and column because of the default mapping.</span></span> <span data-ttu-id="56bc7-104">Se si desidera creare un elemento nello schema XSD di cui non venga eseguito il mapping a qualsiasi tabella (vista) o colonna di database e che non venga visualizzato in XML, è possibile specificare l'annotazione `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="56bc7-104">If you want to create an element in the XSD schema that does not map to any database table (view) or column and that does not appear in the XML, you can specify the `sql:mapped` annotation.</span></span>  
  
 <span data-ttu-id="56bc7-105">L'annotazione `sql:mapped` risulta particolarmente utile se lo schema non può essere modificato o se viene utilizzato per la convalida XML da altre origini pur contenendo dati non archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="56bc7-105">The `sql:mapped` annotation is especially useful if the schema cannot be modified or if the schema is used to validate XML from other sources and yet contains data that is not stored in your database.</span></span> <span data-ttu-id="56bc7-106">La differenza tra l'annotazione `sql:mapped` e `sql:is-constant` consiste nel fatto che gli elementi e gli attributi di cui non è stato eseguito il mapping non vengono visualizzati nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="56bc7-106">The `sql:mapped` annotation differs from `sql:is-constant` in that the unmapped elements and attributes do not appear in the XML document.</span></span>  
  
 <span data-ttu-id="56bc7-107">L'annotazione `sql:mapped` accetta un valore booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="56bc7-107">The `sql:mapped` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="56bc7-108">I valori possibili sono 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="56bc7-108">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="56bc7-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="56bc7-109">Examples</span></span>  
 <span data-ttu-id="56bc7-110">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="56bc7-110">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="56bc7-111">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="56bc7-111">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlmapped-annotation"></a><span data-ttu-id="56bc7-112">R.</span><span class="sxs-lookup"><span data-stu-id="56bc7-112">A.</span></span> <span data-ttu-id="56bc7-113">Specifica dell'annotazione sql:mapped</span><span class="sxs-lookup"><span data-stu-id="56bc7-113">Specifying the sql:mapped annotation</span></span>  
 <span data-ttu-id="56bc7-114">Si supponga di disporre di uno schema XSD di un'altra origine.</span><span class="sxs-lookup"><span data-stu-id="56bc7-114">Assume you have an XSD schema from some other source.</span></span> <span data-ttu-id="56bc7-115">Questo schema XSD è costituito da un **\<Person.Contact>** elemento con gli attributi **ContactID**, **FirstName**, **LastName**e **HomeAddress** .</span><span class="sxs-lookup"><span data-stu-id="56bc7-115">This XSD schema consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, **LastName**, and **HomeAddress** attributes.</span></span>  
  
 <span data-ttu-id="56bc7-116">Per eseguire il mapping di questo schema XSD alla tabella Person. Contact nel database AdventureWorks, `sql:mapped` viene specificato nell'attributo **HomeAddress** perché la tabella Employees non archivia gli indirizzi Home dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="56bc7-116">In mapping this XSD schema to the Person.Contact table in the AdventureWorks database, `sql:mapped` is specified on the **HomeAddress** attribute because the Employees table does not store the home addresses of employees.</span></span> <span data-ttu-id="56bc7-117">Di conseguenza, questo attributo non viene mappato al database e non viene restituito nel documento XML risultante quando viene specificata una query XPath sullo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="56bc7-117">As a result, this attribute is not mapped to the database and is not returned in the resulting XML document when an XPath query is specified against the mapping schema.</span></span>  
  
 <span data-ttu-id="56bc7-118">Per il resto dello schema viene eseguito il mapping predefinito.</span><span class="sxs-lookup"><span data-stu-id="56bc7-118">Default mapping takes place for the rest of the schema.</span></span> <span data-ttu-id="56bc7-119">L' **\<Person.Contact>** elemento viene mappato alla tabella Person. Contact e tutti gli attributi vengono mappati alle colonne con lo stesso nome nella tabella Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="56bc7-119">The **\<Person.Contact>** element maps to the Person.Contact table, and all the attributes map to the columns with the same name in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:attribute name="ContactID"   type="xsd:string"/>  
      <xsd:attribute name="FirstName"    type="xsd:string" />  
      <xsd:attribute name="LastName"     type="xsd:string" />  
      <xsd:attribute name="HomeAddress" type="xsd:string"   
                     sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="56bc7-120">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="56bc7-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="56bc7-121">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="56bc7-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="56bc7-122">Salvare il file con il nome sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="56bc7-122">Save the file as sql-mapped.xml.</span></span>  
  
2.  <span data-ttu-id="56bc7-123">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="56bc7-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="56bc7-124">Salvare il file con il nome sql-mappedT.xml nella stessa directory in cui è stato salvato il file sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="56bc7-124">Save the file as sql-mappedT.xml in the same directory where you saved sql-mapped.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-mapped.xml">  
            /Person.Contact[@ContactID < 10]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="56bc7-125">Il percorso di directory specificato per lo schema di mapping (MySchema.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="56bc7-125">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="56bc7-126">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="56bc7-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-mapped.xml"  
    ```  
  
3.  <span data-ttu-id="56bc7-127">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="56bc7-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="56bc7-128">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="56bc7-128">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="56bc7-129">Set di risultati:</span><span class="sxs-lookup"><span data-stu-id="56bc7-129">This is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel" />   
  <Person.Contact ContactID="3" FirstName="Kim" LastName="Abercrombie" />   
  <Person.Contact ContactID="4" FirstName="Humberto" LastName="Acevedo" />   
  <Person.Contact ContactID="5" FirstName="Pilar" LastName="Ackerman" />   
  <Person.Contact ContactID="6" FirstName="Frances" LastName="Adams" />   
  <Person.Contact ContactID="7" FirstName="Margaret" LastName="Smith" />   
  <Person.Contact ContactID="8" FirstName="Carla" LastName="Adams" />   
  <Person.Contact ContactID="9" FirstName="Jay" LastName="Adams" />   
</ROOT>  
```  
  
 <span data-ttu-id="56bc7-130">Si noti che gli attributi ContactID, FirstName e LastName sono presenti, mentre HomeAdress è assente, in quanto lo schema di mapping specifica il valore 0 per l'attributo `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="56bc7-130">Note that the ContactID, FirstName, and LastName are present, but HomeAddress is not because the mapping schema specified 0 for the `sql:mapped` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56bc7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56bc7-131">See Also</span></span>  
 [<span data-ttu-id="56bc7-132">Mapping predefinito di elementi e attributi XSD a tabelle e colonne &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="56bc7-132">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
  
  
