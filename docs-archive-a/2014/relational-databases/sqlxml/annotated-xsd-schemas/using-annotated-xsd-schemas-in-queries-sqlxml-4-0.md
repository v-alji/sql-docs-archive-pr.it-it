---
title: Utilizzo di schemi XSD con annotazioni nelle query (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML]
- inline schemas [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- queries [SQLXML], annotated XSD schemas
- retrieving data
- mapping schema [SQLXML], queries
- multiple inline schemas
- annotated XSD schemas, queries
- XSD schemas [SQLXML], queries
- templates [SQLXML], annotated XSD schemas in queries
ms.assetid: 927a30a2-eae8-420d-851d-551c5f884f3c
author: rothja
ms.author: jroth
ms.openlocfilehash: c3038ea234f707da7a87a030cb4110510f5a77c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634934"
---
# <a name="using-annotated-xsd-schemas-in-queries-sqlxml-40"></a><span data-ttu-id="775a6-102">Utilizzo di schemi XSD con annotazioni in query (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="775a6-102">Using Annotated XSD Schemas in Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="775a6-103">È possibile specificare query su uno schema con annotazioni per recuperare dati dal database specificando in un modello query XPath sullo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="775a6-103">You can specify queries against an annotated schema to retrieve data from the database by specifying XPath queries in a template against the XSD schema.</span></span>  
  
 <span data-ttu-id="775a6-104">L' **\<sql:xpath-query>** elemento consente di specificare una query XPath sulla vista XML definita dallo schema con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="775a6-104">The **\<sql:xpath-query>** element allows you to specify an XPath query against the XML view that is defined by the annotated schema.</span></span> <span data-ttu-id="775a6-105">Lo schema con annotazioni su cui viene eseguita la query XPath viene identificato tramite l' `mapping-schema` attributo dell' **\<sql:xpath-query>** elemento.</span><span class="sxs-lookup"><span data-stu-id="775a6-105">The annotated schema against which the XPath query is to be executed is identified by using the `mapping-schema` attribute of the **\<sql:xpath-query>** element.</span></span>  
  
 <span data-ttu-id="775a6-106">I modelli sono documenti XML validi che contengono una o più query.</span><span class="sxs-lookup"><span data-stu-id="775a6-106">Templates are valid XML documents that contain one or more queries.</span></span> <span data-ttu-id="775a6-107">Le query FOR XML e XPath restituiscono un frammento del documento.</span><span class="sxs-lookup"><span data-stu-id="775a6-107">The FOR XML and XPath queries return a document fragment.</span></span> <span data-ttu-id="775a6-108">I modelli fungono da contenitori per i frammenti del documento e offrono in tal modo un metodo per specificare un singolo elemento di livello principale.</span><span class="sxs-lookup"><span data-stu-id="775a6-108">Templates act as containers for the document fragments; templates thus provide a way to specify a single, top-level element.</span></span>  
  
 <span data-ttu-id="775a6-109">Negli esempi inclusi in questo argomento vengono utilizzati modelli per specificare una query XPath su uno schema con annotazioni per recuperare dati dal database.</span><span class="sxs-lookup"><span data-stu-id="775a6-109">The examples in this topic use templates to specify an XPath query against an annotated schema to retrieve data from the database.</span></span>  
  
 <span data-ttu-id="775a6-110">Si consideri, ad esempio, lo schema con annotazioni seguente:</span><span class="sxs-lookup"><span data-stu-id="775a6-110">For example, consider this annotated schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID" type="xsd:string" />   
       <xsd:attribute name="FirstName" type="xsd:string" />   
       <xsd:attribute name="LastName"  type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="775a6-111">A scopo illustrativo, lo schema XSD viene archiviato in un file denominato Schema2.xml.</span><span class="sxs-lookup"><span data-stu-id="775a6-111">For the purpose of illustration, this XSD schema is stored in file named Schema2.xml.</span></span> <span data-ttu-id="775a6-112">È quindi possibile specificare una query XPath sullo schema con annotazioni nel file di modello seguente (Schema2T.xml):</span><span class="sxs-lookup"><span data-stu-id="775a6-112">You could then have an XPath query against the annotated schema specified in the following template file (Schema2T.xml):</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql"  
     >  
          Person.Contact[@ContactID="1"]  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="775a6-113">È infine possibile creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire la query come parte di un file di modello.</span><span class="sxs-lookup"><span data-stu-id="775a6-113">You can then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the query as part of a template file.</span></span> <span data-ttu-id="775a6-114">Per ulteriori informazioni, vedere [schemi XDR con Annotazioni &#40;deprecati in SQLXML 4,0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="775a6-114">For more information, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="using-inline-mapping-schemas"></a><span data-ttu-id="775a6-115">Utilizzo di schemi di mapping inline</span><span class="sxs-lookup"><span data-stu-id="775a6-115">Using Inline Mapping Schemas</span></span>  
 <span data-ttu-id="775a6-116">È possibile includere uno schema con annotazioni direttamente in un modello e quindi specificare nel modello una query XPath sullo schema inline.</span><span class="sxs-lookup"><span data-stu-id="775a6-116">An annotated schema can be included directly in a template, and then an XPath query can be specified in the template against the inline schema.</span></span> <span data-ttu-id="775a6-117">Il modello può essere anche un updategram.</span><span class="sxs-lookup"><span data-stu-id="775a6-117">The template can also be an updategram.</span></span>  
  
 <span data-ttu-id="775a6-118">Un modello può includere più schemi inline.</span><span class="sxs-lookup"><span data-stu-id="775a6-118">A template can include multiple inline schemas.</span></span> <span data-ttu-id="775a6-119">Per utilizzare uno schema inline incluso in un modello, specificare l'attributo **ID** con un valore univoco nell' **\<xsd:schema>** elemento, quindi utilizzare **#idvalue** per fare riferimento allo schema inline.</span><span class="sxs-lookup"><span data-stu-id="775a6-119">To use an inline schema that is included in a template, specify the **id** attribute with a unique value on the **\<xsd:schema>** element, and then use **#idvalue** to reference the inline schema.</span></span> <span data-ttu-id="775a6-120">Il comportamento dell'attributo **ID** è identico a quello di **SQL: ID** ({urn: schemas-microsoft-com: XML-SQL} ID) utilizzato negli schemi XDR.</span><span class="sxs-lookup"><span data-stu-id="775a6-120">The **id** attribute is identical in behavior to the **sql:id** ({urn:schemas-microsoft-com:xml-sql}id) used in XDR schemas.</span></span>  
  
 <span data-ttu-id="775a6-121">Nel modello seguente, ad esempio, vengono specificati due schemi con annotazioni inline:</span><span class="sxs-lookup"><span data-stu-id="775a6-121">For example, the following template specifies two inline-annotated schemas:</span></span>  
  
```  
<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'>  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema1' sql:is-mapping-schema='1'>  
  <xsd:element name='Employees' ms:relation='HumanResources.Employee'>  
    <xsd:complexType>  
      <xsd:attribute name='LoginID'   
                     type='xsd:string'/>  
      <xsd:attribute name='Title'   
                     type='xsd:string'/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema2' sql:is-mapping-schema='1'>  
  <xsd:element name='Contacts' ms:relation='Person.Contact'>  
    <xsd:complexType>  
  
      <xsd:attribute name='ContactID'   
                     type='xsd:string' />  
      <xsd:attribute name='FirstName'   
                     type='xsd:string' />  
      <xsd:attribute name='LastName'   
                     type='xsd:string' />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema1'>  
    /Employees[@LoginID='adventure-works\guy1']  
</sql:xpath-query>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema2'>  
    /Contacts[@ContactID='1']  
</sql:xpath-query>  
</ROOT>  
```  
  
 <span data-ttu-id="775a6-122">Il modello specifica inoltre due query XPath.</span><span class="sxs-lookup"><span data-stu-id="775a6-122">The template also specifies two XPath queries.</span></span> <span data-ttu-id="775a6-123">Ogni **\<xpath-query>** elemento identifica in modo univoco lo schema di mapping specificando l' `mapping-schema` attributo.</span><span class="sxs-lookup"><span data-stu-id="775a6-123">Each of the **\<xpath-query>** elements uniquely identifies the mapping schema by specifying the `mapping-schema` attribute.</span></span>  
  
 <span data-ttu-id="775a6-124">Quando si specifica uno schema inline nel modello, è `sql:is-mapping-schema` necessario specificare anche l'annotazione nell' **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="775a6-124">When you specify an inline schema in the template, the `sql:is-mapping-schema` annotation must also be specified on the **\<xsd:schema>** element.</span></span> <span data-ttu-id="775a6-125">`sql:is-mapping-schema` utilizza un valore booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="775a6-125">The `sql:is-mapping-schema` takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="775a6-126">Uno schema inline con **SQL: is-mapping-schema = "1"** viene considerato come schema con annotazioni inline e non viene restituito nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="775a6-126">An inline schema with **sql:is-mapping-schema="1"** is treated as inline annotated schema and is not returned in the XML document.</span></span>  
  
 <span data-ttu-id="775a6-127">L'annotazione `sql:is-mapping-schema` appartiene allo spazio dei nomi del modello `urn:schemas-microsoft-com:xml-sql`.</span><span class="sxs-lookup"><span data-stu-id="775a6-127">The `sql:is-mapping-schema` annotation belongs to the template namespace `urn:schemas-microsoft-com:xml-sql`.</span></span>  
  
 <span data-ttu-id="775a6-128">Per testare questo esempio, salvare il modello (InlineSchemaTemplate.xml) in una directory locale, quindi creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="775a6-128">To test this example, save the template (InlineSchemaTemplate.xml) in a local directory and then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="775a6-129">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="775a6-129">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="775a6-130">Oltre a specificare l' `mapping-schema` attributo nell' **\<sql:xpath-query>** elemento in un modello (quando è presente una query XPath) o nell' **\<updg:sync>** elemento in un updategram, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="775a6-130">In addition to specifying the `mapping-schema` attribute on the **\<sql:xpath-query>** element in a template (when there is an XPath query), or on **\<updg:sync>** element in an updategram, you can do the following:</span></span>  
  
-   <span data-ttu-id="775a6-131">Specificare l' `mapping-schema` attributo **\<ROOT>** nell'elemento (dichiarazione globale) nel modello.</span><span class="sxs-lookup"><span data-stu-id="775a6-131">Specify the `mapping-schema` attribute on the **\<ROOT>** element (global declaration) in the template.</span></span> <span data-ttu-id="775a6-132">Questo schema di mapping diventa quindi lo schema predefinito che verrà utilizzato da tutti i nodi XPath e updategram che non dispongono di alcuna annotazione `mapping-schema` esplicita.</span><span class="sxs-lookup"><span data-stu-id="775a6-132">This mapping schema then becomes the default schema that will be used by all XPath and updategram nodes that have no explicit `mapping-schema` annotation.</span></span>  
  
-   <span data-ttu-id="775a6-133">Specificare l'attributo `mapping schema` utilizzando l'oggetto ADO `Command`.</span><span class="sxs-lookup"><span data-stu-id="775a6-133">Specify the `mapping schema` attribute by using the ADO `Command` object.</span></span>  
  
 <span data-ttu-id="775a6-134">L' `mapping-schema` attributo specificato nell' **\<xpath-query>** **\<updg:sync>** elemento o ha la precedenza più alta `Command` . l'oggetto ADO ha la precedenza più bassa.</span><span class="sxs-lookup"><span data-stu-id="775a6-134">The `mapping-schema` attribute that is specified on the **\<xpath-query>** or **\<updg:sync>** element has the highest precedence; the ADO `Command` object has the lowest precedence.</span></span>  
  
 <span data-ttu-id="775a6-135">Si noti che se si specifica una query XPath in un modello e non si specifica uno schema di mapping sul quale viene eseguita la query XPath, la query XPath viene considerata come una query di tipo **dbobject** .</span><span class="sxs-lookup"><span data-stu-id="775a6-135">Note that if you specify an XPath query in a template and do not specify a mapping schema against which the XPath query is executed, the XPath query is treated as a **dbobject** type query.</span></span> <span data-ttu-id="775a6-136">Considerare ad esempio il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="775a6-136">For example, consider this template:</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql">  
          Production.ProductPhoto[@ProductPhotoID='100']/@LargePhoto  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="775a6-137">Il modello specifica una query XPath ma non specifica uno schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="775a6-137">The template specifies an XPath query but it does not specify a mapping schema.</span></span> <span data-ttu-id="775a6-138">Questa query viene pertanto considerata una query di tipo **dbobject** in cui Production. ProductPhoto è il nome della tabella e @ProductPhotoID =' 100' è un predicato che trova una foto del prodotto con valore ID 100.</span><span class="sxs-lookup"><span data-stu-id="775a6-138">Therefore, this query is treated as a **dbobject** type query in which Production.ProductPhoto is the table name and @ProductPhotoID='100' is a predicate that finds a product photo with the ID value of 100.</span></span> <span data-ttu-id="775a6-139">@LargePhotocolonna da cui recuperare il valore.</span><span class="sxs-lookup"><span data-stu-id="775a6-139">@LargePhoto is the column from which to retrieve the value.</span></span>  
  
  
