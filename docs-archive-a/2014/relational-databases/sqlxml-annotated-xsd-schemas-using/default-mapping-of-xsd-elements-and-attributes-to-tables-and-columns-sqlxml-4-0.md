---
title: Mapping predefinito di elementi e attributi XSD a tabelle e colonne (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XSD schemas [SQLXML], mapping attributes and elements
- mapping schema [SQLXML], default mapping
- element mapping [SQLXML], default mapping
- element mapping [SQLXML]
- table mapping [SQLXML]
- annotated XSD schemas, mapping attributes and elements
- table/view mapping [SQLXML]
- column mapping [SQLXML]
- attribute mapping [SQLXML], default mapping
- default schema mapping
- table mapping [SQLXML], default mapping
- testing XPath query against schema
- xml data type [SQL Server], SQLXML
- table/view mapping [SQLXML], default mapping
- element/attribute mapping [SQLXML]
ms.assetid: 9a18e92a-6cfb-4a14-993a-663a95aabb63
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bccec2413e8a0a6e13283a0f3e5f63ab61e934b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628606"
---
# <a name="default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="67815-102">Mapping predefinito di elementi e attributi XSD a tabelle e colonne (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="67815-102">Default Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="67815-103">Per impostazione predefinita, viene eseguito il mapping di un elemento di tipo complesso in uno schema XSD con annotazioni alla tabella (vista) con lo stesso nome nel database specificato e di un elemento o un attributo di tipo semplice alla colonna con lo stesso nome nella tabella.</span><span class="sxs-lookup"><span data-stu-id="67815-103">By default, an element of complex type in an XSD annotated schema maps to the table (view) with the same name in the specified database, and an element or attribute of simple type maps to the column with the same name in the table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="67815-104">Esempi</span><span class="sxs-lookup"><span data-stu-id="67815-104">Examples</span></span>  
 <span data-ttu-id="67815-105">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="67815-105">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="67815-106">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="67815-106">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-default-mapping"></a><span data-ttu-id="67815-107">R.</span><span class="sxs-lookup"><span data-stu-id="67815-107">A.</span></span> <span data-ttu-id="67815-108">Definizione del mapping predefinito</span><span class="sxs-lookup"><span data-stu-id="67815-108">Specifying default mapping</span></span>  
 <span data-ttu-id="67815-109">In questo esempio non viene specificata alcuna annotazione nello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="67815-109">In this example, no annotations are specified in the XSD schema.</span></span> <span data-ttu-id="67815-110">L' **\<Person.Contact>** elemento è di tipo complesso e, pertanto, esegue il mapping per impostazione predefinita alla tabella Person. Contact del database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="67815-110">The **\<Person.Contact>** element is of complex type and, therefore, maps by default to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="67815-111">Tutti gli attributi (ContactID, FirstName, LastName) dell' **\<Person.Contact>** elemento sono di tipo semplice ed eseguono il mapping per impostazione predefinita alle colonne con gli stessi nomi nella tabella Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="67815-111">All the attributes (ContactID, FirstName, LastName) of the **\<Person.Contact>** element are of simple type and map by default to columns with the same names in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  type="xsd:string" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="67815-112">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="67815-112">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="67815-113">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="67815-113">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="67815-114">Salvare il file con il nome MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="67815-114">Save the file as MySchema.xml.</span></span>  
  
2.  <span data-ttu-id="67815-115">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="67815-115">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="67815-116">Salvare il file con il nome MySchemaT.xml nella stessa directory in cui è stato salvato il file MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="67815-116">Save the file as MySchemaT.xml in the same directory where you saved MySchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchema.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="67815-117">Il percorso di directory specificato per lo schema di mapping (MySchema.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="67815-117">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="67815-118">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="67815-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema.xml"  
    ```  
  
3.  <span data-ttu-id="67815-119">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="67815-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="67815-120">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="67815-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="67815-121">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="67815-121">Here is the partial result set:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8" ?>  
<ROOT>  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong"/>  
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel"/>  
   ...  
</ROOT>  
```  
  
### <a name="b-mapping-an-xml-element-to-a-database-column"></a><span data-ttu-id="67815-122">B.</span><span class="sxs-lookup"><span data-stu-id="67815-122">B.</span></span> <span data-ttu-id="67815-123">Mapping di un elemento XML a una colonna del database</span><span class="sxs-lookup"><span data-stu-id="67815-123">Mapping an XML element to a database column</span></span>  
 <span data-ttu-id="67815-124">Anche in questo esempio viene eseguito un mapping predefinito, in quanto non viene utilizzata alcuna annotazione.</span><span class="sxs-lookup"><span data-stu-id="67815-124">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="67815-125">L' **\<Person.Contact>** elemento è di tipo complesso e viene mappato alla tabella con lo stesso nome nel database.</span><span class="sxs-lookup"><span data-stu-id="67815-125">The **\<Person.Contact>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="67815-126">Gli elementi **\<FirstName>** e e **\<LastName>** l'attributo **EmployeeID** sono di tipo semplice e, pertanto, eseguono il mapping alle colonne con gli stessi nomi.</span><span class="sxs-lookup"><span data-stu-id="67815-126">The elements **\<FirstName>** and **\<LastName>** and the **EmployeeID** attribute are of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="67815-127">L'unica differenza tra questo e l'esempio precedente consiste nel fatto che gli elementi vengono utilizzati per eseguire il mapping dei campi FirstName e LastName.</span><span class="sxs-lookup"><span data-stu-id="67815-127">The only difference between this and the previous example are that elements are used for mapping the FirstName and LastName fields.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="FirstName" type="xsd:string" />   
        <xsd:element name="LastName" type="xsd:string" />   
      </xsd:sequence>  
      <xsd:attribute name="ContactID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="67815-128">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="67815-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="67815-129">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="67815-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="67815-130">Salvare il file con il nome MySchemaElements.xml.</span><span class="sxs-lookup"><span data-stu-id="67815-130">Save the file as MySchemaElements.xml.</span></span>  
  
2.  <span data-ttu-id="67815-131">Creare il modello seguente (MySchemaElementsT.xml) e salvarlo nella stessa directory utilizzata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="67815-131">Create the following template (MySchemaElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaElements.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="67815-132">Il percorso di directory specificato per lo schema di mapping è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="67815-132">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="67815-133">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="67815-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaElements.xml"  
    ```  
  
3.  <span data-ttu-id="67815-134">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="67815-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="67815-135">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="67815-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="67815-136">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="67815-136">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1">  
    <FirstName>Gustavo</FirstName>  
    <LastName>Achong</LastName>  
  </Person.Contact>  
   ...  
</ROOT>  
```  
  
### <a name="c-mapping-an-xml-element-to-an-xml-data-type-column"></a><span data-ttu-id="67815-137">C.</span><span class="sxs-lookup"><span data-stu-id="67815-137">C.</span></span> <span data-ttu-id="67815-138">Mapping di un elemento XML a una colonna con tipo di dati XML</span><span class="sxs-lookup"><span data-stu-id="67815-138">Mapping an XML element to an XML data type column</span></span>  
 <span data-ttu-id="67815-139">Anche in questo esempio viene eseguito un mapping predefinito, in quanto non viene utilizzata alcuna annotazione.</span><span class="sxs-lookup"><span data-stu-id="67815-139">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="67815-140">L' **\<Production.ProductModel>** elemento è di tipo complesso e viene mappato alla tabella con lo stesso nome nel database.</span><span class="sxs-lookup"><span data-stu-id="67815-140">The **\<Production.ProductModel>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="67815-141">L'attributo **ProductModelID** è di tipo semplice e, pertanto, viene mappato alle colonne con gli stessi nomi.</span><span class="sxs-lookup"><span data-stu-id="67815-141">The **ProductModelID** attribute is of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="67815-142">L'unica differenza tra questo e gli esempi precedenti è che l' **\<Instructions>** elemento sta eseguendo il mapping a una colonna che utilizza il `xml` tipo di dati utilizzando il `xsd:anyType` tipo.</span><span class="sxs-lookup"><span data-stu-id="67815-142">The only difference between this and the previous examples is that the **\<Instructions>** element is mapping to a column that uses the `xml` data type by using the `xsd:anyType` type.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Instructions" type="xsd:anyType" />   
      </xsd:sequence>  
      <xsd:attribute name="ProductModelID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="67815-143">Il tipo di dati `xml` è stato introdotto in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67815-143">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="67815-144">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="67815-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="67815-145">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="67815-145">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="67815-146">Salvare il file con il nome MySchemaXmlAnyElements.xml.</span><span class="sxs-lookup"><span data-stu-id="67815-146">Save the file as MySchemaXmlAnyElements.xml.</span></span>  
  
2.  <span data-ttu-id="67815-147">Creare il modello seguente (MySchemaXmlAnyElementsT.xml) e salvarlo nella stessa directory utilizzata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="67815-147">Create the following template (MySchemaXmlAnyElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaXmlAnyElements.xml">  
            /Production.ProductModel[@ProductModelID=7]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="67815-148">Il percorso di directory specificato per lo schema di mapping è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="67815-148">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="67815-149">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="67815-149">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaXmlAnyElements.xml"  
    ```  
  
3.  <span data-ttu-id="67815-150">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="67815-150">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="67815-151">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="67815-151">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="67815-152">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="67815-152">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductModel ProductModelID="7">  
    <Instructions>  
      <root xmlns="http:  
//schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstru  
ctions">  
...  
      </root>  
    <Instructions>  
  </Production.ProductModel>  
</ROOT>  
```  
  
## <a name="see-also"></a><span data-ttu-id="67815-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67815-153">See Also</span></span>  
 <span data-ttu-id="67815-154">[Considerazioni sulla sicurezza dello schema con annotazioni &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="67815-154">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="67815-155">[Dati XML &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67815-155">[XML Data &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span></span>  
 [<span data-ttu-id="67815-156">Supporto del tipo di dati xml in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="67815-156">xml Data Type Support in SQLXML 4.0</span></span>](../sqlxml/xml-data-type-support-in-sqlxml-4-0.md)  
  
  
