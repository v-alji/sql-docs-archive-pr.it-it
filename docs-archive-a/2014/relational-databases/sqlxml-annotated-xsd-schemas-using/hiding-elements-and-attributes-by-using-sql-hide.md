---
title: 'Nascondere elementi e attributi tramite SQL: Hide | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- hiding elements
- element mapping [SQLXML], hiding attributes and elements
- hide annotation
- sql:hide
- table/view mapping [SQLXML], hiding attributes and elements
- table mapping [SQLXML], hiding attributes and elements
- hiding attributes
- annotated XSD schemas, hiding attributes and elements
- attribute mapping [SQLXML], hiding attributes and elements
- column mapping [SQLXML]
- element hiding [SQLXML]
- XSD schemas [SQLXML], hiding attributes and elements
- attribute hiding [SQLXML]
ms.assetid: 0978301b-f068-46b6-82b9-dc555161f52e
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a3beb48be1d9809b170faeafa964ba45156ac28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725351"
---
# <a name="hiding-elements-and-attributes-by-using-sqlhide"></a><span data-ttu-id="79bee-102">Nascondere gli elementi e gli attributi utilizzando sql:hide</span><span class="sxs-lookup"><span data-stu-id="79bee-102">Hiding Elements and Attributes by Using sql:hide</span></span>
  <span data-ttu-id="79bee-103">Quando viene eseguita una query XPath su uno schema XSD, il documento XML risultante presenterà gli elementi e gli attributi specificati nello schema.</span><span class="sxs-lookup"><span data-stu-id="79bee-103">When an XPath query is executed against an XSD schema, the resulting XML document has elements and attributes that are specified in the schema.</span></span> <span data-ttu-id="79bee-104">È possibile specificare che alcuni elementi e attributi siano nascosti nello schema utilizzando l'annotazione `sql:hide`.</span><span class="sxs-lookup"><span data-stu-id="79bee-104">You can specify that some elements and attributes be hidden in the schema by using the `sql:hide` annotation.</span></span> <span data-ttu-id="79bee-105">Ciò si rivela utile quando i criteri di selezione della query richiedono determinati elementi o attributi dello schema, ma non si desidera che vengano restituiti nel documento XML generato.</span><span class="sxs-lookup"><span data-stu-id="79bee-105">This is useful when the selection criteria of the query require particular elements or attributes in the schema, but you do not want them returned in the XML document that is generated.</span></span>  
  
 <span data-ttu-id="79bee-106">L'annotazione `sql:hide` utilizza un valore booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="79bee-106">The `sql:hide` annotation takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="79bee-107">I valori possibili sono 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="79bee-107">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="79bee-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="79bee-108">Examples</span></span>  
 <span data-ttu-id="79bee-109">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="79bee-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="79bee-110">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="79bee-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlhide-on-an-attribute"></a><span data-ttu-id="79bee-111">R.</span><span class="sxs-lookup"><span data-stu-id="79bee-111">A.</span></span> <span data-ttu-id="79bee-112">Specifica di sql:hide in un attributo</span><span class="sxs-lookup"><span data-stu-id="79bee-112">Specifying sql:hide on an attribute</span></span>  
 <span data-ttu-id="79bee-113">Lo schema XSD in questo esempio è costituito da un **\<Person.Contact>** elemento con gli attributi **ContactID**, **FirstName**e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="79bee-113">The XSD schema in this example consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span>  
  
 <span data-ttu-id="79bee-114">L' **\<Person.Contact>** elemento è di tipo complesso e, pertanto, esegue il mapping alla tabella con lo stesso nome (mapping predefinito).</span><span class="sxs-lookup"><span data-stu-id="79bee-114">The **\<Person.Contact>** element is of complex type and, therefore, maps to the table of the same name (default mapping).</span></span> <span data-ttu-id="79bee-115">Tutti gli attributi dell' **\<Person.Contact>** elemento sono di tipo semplice ed eseguono il mapping alle colonne con gli stessi nomi di PERSON. contactTable nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="79bee-115">All the attributes of **\<Person.Contact>** element are of simple type and map to columns with the same names in the Person.Contacttable in the AdventureWorks database.</span></span> <span data-ttu-id="79bee-116">Nello schema l' `sql:hide` annotazione viene specificata nell'attributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="79bee-116">In the schema, the `sql:hide` annotation is specified on the **ContactID** attribute.</span></span> <span data-ttu-id="79bee-117">Quando si specifica una query XPath su questo schema, **ContactID** non viene restituito nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="79bee-117">When an XPath query is specified against this schema, the **ContactID** is not returned in the XML document.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  sql:hide="true" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="79bee-118">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="79bee-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="79bee-119">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="79bee-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="79bee-120">Salvare il file come Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="79bee-120">Save the file as Hide.xml.</span></span>  
  
2.  <span data-ttu-id="79bee-121">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="79bee-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="79bee-122">Salvare il file come HideT.xml nella stessa directory nella quale è stato salvato Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="79bee-122">Save the file as HideT.xml in the same directory where you saved Hide.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Hide.xml">  
            /Person.Contact[@ContactID="1"]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="79bee-123">Il percorso della directory specificato per lo schema di mapping (Hide.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="79bee-123">The directory path specified for the mapping schema (Hide.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="79bee-124">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="79bee-124">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\Hide.xml"  
    ```  
  
3.  <span data-ttu-id="79bee-125">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="79bee-125">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="79bee-126">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="79bee-126">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="79bee-127">Set di risultati:</span><span class="sxs-lookup"><span data-stu-id="79bee-127">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <Person.Contact FirstName="Gustavo" LastName="Achong" />   
</ROOT>  
```  
  
 <span data-ttu-id="79bee-128">Quando viene specificato `sql:hide` in un elemento, questo e i relativi attributi o elementi figlio non vengono visualizzati nel documento XML generato.</span><span class="sxs-lookup"><span data-stu-id="79bee-128">When `sql:hide` is specified on an element, the element and its attributes or child elements do not appear in the XML document that is generated.</span></span> <span data-ttu-id="79bee-129">Di seguito è riportato un altro schema XSD nel quale `sql:hide` viene specificato nell' **\<OD>** elemento:</span><span class="sxs-lookup"><span data-stu-id="79bee-129">Here is another XSD schema in which `sql:hide` is specified on the **\<OD>** element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:annotation>  
    <xsd:documentation>  
      Sales.Customer-Sales.SalesOrderHeader-Sales.SalesOrderDetail Schema  
      Copyright 2004 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="CustomerOrder"  
         parent="Sales.Customer"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Sales.SalesOrderHeader" />  
       <sql:relationship name="OrderOrderDetails"  
                  parent="Sales.SalesOrderHeader"  
                  parent-key="SalesOrderID"  
                  child-key="SalesOrderID"  
                  child="Sales.SalesOrderDetail"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Sales.Customer">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
                     maxOccurs="unbounded"   
                     sql:relationship="CustomerOrder">  
          <xsd:complexType>  
            <xsd:sequence>  
               <xsd:element name="OD" sql:relation="Sales.SalesOrderDetail"                                       maxOccurs="unbounded"                                       sql:relationship="OrderOrderDetails"                                       sql:hide="1">  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:string"/>  
                    <xsd:attribute name="ProductID" type="xsd:string"/>  
                  </xsd:complexType>  
               </xsd:element>  
            </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string"/>  
          <xsd:attribute name="OID" sql:field="SalesOrderID"   
                                    type="xsd:string"/>  
          <xsd:attribute name="OrderDate" type="xsd:date"/>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CID" sql:field="CustomerID"   
                                type="xsd:string"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="79bee-130">Quando si specifica una query XPath (ad esempio `/Customers[@CID="1"]` ) su questo schema, il documento XML generato non include l' **\<OD>** elemento e i relativi elementi figlio, come illustrato in questo risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="79bee-130">When an XPath query (for example `/Customers[@CID="1"]`) is specified against this schema, the XML document that is generated does not include the **\<OD>** element and its children, as shown in this partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers CID="1">  
    <Order CustomerID="1" OID="43860" OrderDate="2001-08-01" />   
    <Order CustomerID="1" OID="44501" OrderDate="2001-11-01" />   
    <Order CustomerID="1" OID="45283" OrderDate="2002-02-01" />   
    <Order CustomerID="1" OID="46042" OrderDate="2002-05-01" />   
  </Customers>  
</ROOT>  
```  
  
  
