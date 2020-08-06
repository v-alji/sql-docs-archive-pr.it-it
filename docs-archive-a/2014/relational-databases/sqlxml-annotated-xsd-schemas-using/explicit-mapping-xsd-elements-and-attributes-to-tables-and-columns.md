---
title: Mapping esplicito di elementi e attributi XSD a tabelle e colonne (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- sql:field
- row mapping [SQLXML]
- attribute mapping [SQLXML], explicit mapping
- field annotation
- XSD schemas [SQLXML], mapping attributes and elements
- names [SQLXML]
- relation annotation
- table/view mapping [SQLXML], explicit mapping
- sql:relation
- mapping schema [SQLXML], explicit mapping
- annotated XSD schemas, mapping attributes and elements
- column mapping [SQLXML]
- element mapping [SQLXML], explicit mapping
- table mapping [SQLXML], explicit mapping
- element/attribute mapping [SQLXML]
ms.assetid: 7a5ebeb6-7322-4141-a307-ebcf95976146
author: rothja
ms.author: jroth
ms.openlocfilehash: f3400682b5f28835ca039912aab058691929a6c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625258"
---
# <a name="explicit-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="2e2f9-102">Mapping esplicito di attributi ed elementi XSD a tabelle e colonne (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2e2f9-102">Explicit Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="2e2f9-103">Quando si utilizza uno schema XSD per fornire una vista XML del database relazionale, è necessario eseguire il mapping degli elementi e degli attributi dello schema a tabelle e colonne del database.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-103">When using an XSD schema to provide an XML view of the relational database , the elements and attributes of the schema must be mapped to tables and columns of the database.</span></span> <span data-ttu-id="2e2f9-104">Le righe della tabella/vista di database vengono mappate agli elementi del documento XML.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-104">The rows in the database table/view will map to elements in the XML document.</span></span> <span data-ttu-id="2e2f9-105">I valori di colonna del database vengono mappati agli attributi o agli elementi.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-105">The column values in the database map to attributes or elements.</span></span>  
  
 <span data-ttu-id="2e2f9-106">Quando vengono specificate query XPath nello schema XSD con annotazioni, i dati relativi agli elementi e agli attributi dello schema vengono recuperati dalle tabelle e dalle colonne alle quali vengono mappati.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-106">When XPath queries are specified against the annotated XSD schema, the data for the elements and attributes in the schema is retrieved from the tables and columns to which they map.</span></span> <span data-ttu-id="2e2f9-107">Per ottenere un solo valore dal database, per il mapping specificato nello schema XSD devono essere indicati sia la relazione che il campo.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-107">To obtain a single value from the database, the mapping specified in the XSD schema must have both relation and field specification.</span></span> <span data-ttu-id="2e2f9-108">Se il nome di un elemento/attributo non corrisponde a quello della tabella/colonna a cui viene eseguito il mapping, vengono utilizzate le annotazioni `sql:relation` e `sql:field` per specificare il mapping tra un elemento o un attributo di un documento XML e la tabella (vista) o colonna di un database.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-108">If the name of an element/attribute is not the same name as the table/view or column name to which it maps, the `sql:relation` and `sql:field` annotations are used to specify the mapping between an element or attribute in an XML document and the table (view) or column in a database.</span></span>  
  
## <a name="sql-relation"></a><span data-ttu-id="2e2f9-109">sql-relation</span><span class="sxs-lookup"><span data-stu-id="2e2f9-109">sql-relation</span></span>  
 <span data-ttu-id="2e2f9-110">L'annotazione `sql:relation` viene aggiunta per eseguire il mapping di un nodo XML dello schema XSD a una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-110">The `sql:relation` annotation is added to map an XML node in the XSD schema to a database table.</span></span> <span data-ttu-id="2e2f9-111">Il nome di una tabella (vista) viene specificato come valore dell'annotazione `sql:relation`.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-111">The name of a table (view) is specified as the value of the `sql:relation` annotation.</span></span>  
  
 <span data-ttu-id="2e2f9-112">Quando `sql:relation` viene specificata su un elemento, l'ambito di questa annotazione si applica a tutti gli attributi e gli elementi figlio descritti nella definizione dei tipi complessi di quell'elemento, rendendo in questo modo più veloce la scrittura di annotazioni.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-112">When `sql:relation` is specified on an element, the scope of this annotation applies to all attributes and child elements that are described in the complex type definition of that element, therefore providing a shortcut in writing annotations.</span></span>  
  
 <span data-ttu-id="2e2f9-113">L' `sql:relation` annotazione è utile anche quando gli identificatori validi in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non sono validi in XML.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-113">The `sql:relation` annotation is also useful when identifiers that are valid in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are not valid in XML.</span></span> <span data-ttu-id="2e2f9-114">"Order Details", ad esempio, è un nome di tabella valido in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ma non in XML.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-114">For example, "Order Details" is a valid table name in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but not in XML.</span></span> <span data-ttu-id="2e2f9-115">In queste situazioni, l'annotazione `sql:relation` può essere utilizzata per specificare il mapping, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2e2f9-115">In such cases, the `sql:relation` annotation can be used to specify the mapping, for example:</span></span>  
  
```  
<xsd:element name="OD" sql:relation="[Order Details]">  
```  
  
## <a name="sql-field"></a><span data-ttu-id="2e2f9-116">sql-field</span><span class="sxs-lookup"><span data-stu-id="2e2f9-116">sql-field</span></span>  
 <span data-ttu-id="2e2f9-117">L'annotazione `sql-field` esegue il mapping di un elemento o attributo a una colonna di database.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-117">The `sql-field` annotation maps an element or attribute to a database column.</span></span> <span data-ttu-id="2e2f9-118">L'annotazione `sql:field` viene aggiunta per eseguire il mapping di un nodo XML nello schema a una colonna di database.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-118">The `sql:field` annotation is added to map an XML node in the schema to a database column.</span></span> <span data-ttu-id="2e2f9-119">Non è possibile specificare `sql:field` su un elemento di contenuto vuoto.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-119">You cannot specify `sql:field` on an empty content element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2e2f9-120">Esempi</span><span class="sxs-lookup"><span data-stu-id="2e2f9-120">Examples</span></span>  
 <span data-ttu-id="2e2f9-121">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-121">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="2e2f9-122">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="2e2f9-122">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelation-and-sqlfield-annotations"></a><span data-ttu-id="2e2f9-123">R.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-123">A.</span></span> <span data-ttu-id="2e2f9-124">Specifica delle annotazioni sql:relation e sql:field</span><span class="sxs-lookup"><span data-stu-id="2e2f9-124">Specifying the sql:relation and sql:field annotations</span></span>  
 <span data-ttu-id="2e2f9-125">In questo esempio lo schema XSD è costituito da un **\<Contact>** elemento di tipo complesso **\<FName>** con **\<LName>** gli elementi figlio e e l'attributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="2e2f9-125">In this example, the XSD schema consists of an **\<Contact>** element of complex type with **\<FName>** and **\<LName>** child elements and the **ContactID** attribute.</span></span>  
  
 <span data-ttu-id="2e2f9-126">L' `sql:relation` annotazione esegue il mapping dell' **\<Contact>** elemento alla tabella Person. Contact del database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-126">The `sql:relation` annotation maps the **\<Contact>** element to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="2e2f9-127">L' `sql:field` annotazione esegue il mapping dell' **\<FName>** elemento alla colonna FirstName e dell' **\<LName>** elemento alla colonna LastName.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-127">The `sql:field` annotation maps the **\<FName>** element to the FirstName column and the **\<LName>** element to the LastName column.</span></span>  
  
 <span data-ttu-id="2e2f9-128">Non è stata specificata alcuna annotazione per l'attributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="2e2f9-128">No annotation is specified for the **ContactID** attribute.</span></span> <span data-ttu-id="2e2f9-129">Il risultato ottenuto è un mapping predefinito dell'attributo alla colonna con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-129">This results in a default mapping of the attribute to the column with the same name.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="2e2f9-130">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="2e2f9-130">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="2e2f9-131">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="2e2f9-132">Salvare il file con il nome MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-132">Save the file as MySchema-annotated.xml.</span></span>  
  
2.  <span data-ttu-id="2e2f9-133">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-133">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="2e2f9-134">Salvare il file con il nome MySchema-annotatedT.xml nella stessa directory in cui è stato salvato il file MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-134">Save the file as MySchema-annotatedT.xml in the same directory where you saved MySchema-annotated.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="MySchema-annotated.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="2e2f9-135">Il percorso della directory specificato per lo schema di mapping MySchema-annotated.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-135">The directory path specified for the mapping schema (MySchema-annotated.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="2e2f9-136">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2e2f9-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema-annotated.xml"  
    ```  
  
3.  <span data-ttu-id="2e2f9-137">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="2e2f9-138">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2e2f9-138">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="2e2f9-139">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="2e2f9-139">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
 <Contact ContactID="1">   
    <FName>Gustavo</FName>   
    <LName>Achong</LName>   
 </Contact>   
  .....  
</ROOT>  
```  
  
  
