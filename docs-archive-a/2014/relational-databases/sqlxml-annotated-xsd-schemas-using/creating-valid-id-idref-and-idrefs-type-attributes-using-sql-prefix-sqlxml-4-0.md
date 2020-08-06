---
title: 'Creazione di attributi di tipo ID, IDREF e IDREFS validi con SQL: prefix (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- annotated XSD schemas, ID type attribute
- IDREF type attribute [SQLXML]
- annotated XSD schemas, IDREFS type attribute
- ID type attribute [SQLXML]
- sql:prefix
- prefix annotation
- IDREF relationships [SQLXML]
- IDREFS type attribute [SQLXML]
- annotated XSD schemas, IDREF type attribute
- ID relationships [SQLXML]
ms.assetid: 1c7f77d3-81f3-4820-bb63-c4aaa4ea9aa1
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9e63bebd0cebbfeed75ea5cbe2ea62683234fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628608"
---
# <a name="creating-valid-id-idref-and-idrefs-type-attributes-using-sqlprefix-sqlxml-40"></a><span data-ttu-id="25863-102">Creazione di attributi di tipo ID, IDREF e IDREFS validi mediante sql:prefix (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="25863-102">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix (SQLXML 4.0)</span></span>
  <span data-ttu-id="25863-103">È possibile specificare un attributo come attributo di tipo ID.</span><span class="sxs-lookup"><span data-stu-id="25863-103">An attribute can be specified to be an ID type attribute.</span></span> <span data-ttu-id="25863-104">Gli attributi specificati come IDREF o IDREFS possono essere quindi utilizzati per fare riferimento agli attributi di tipo ID, in modo da abilitare i collegamenti tra i documenti.</span><span class="sxs-lookup"><span data-stu-id="25863-104">Attributes specified as IDREF or IDREFS can then be used to refer to the ID type attributes, enabling links between documents.</span></span>  
  
 <span data-ttu-id="25863-105">ID, IDREF e IDREFS corrispondono alle relazioni PK/FK (chiave primaria/chiave esterna) nel database, con poche differenze.</span><span class="sxs-lookup"><span data-stu-id="25863-105">ID, IDREF, and IDREFS correspond to PK/FK (primary key/foreign key) relationships in the database, with few differences.</span></span> <span data-ttu-id="25863-106">In un documento XML i valori degli attributi di tipo ID devono essere distinti.</span><span class="sxs-lookup"><span data-stu-id="25863-106">In an XML document, the values of ID type attributes must be distinct.</span></span> <span data-ttu-id="25863-107">Se gli attributi **CustomerID** e **OrderID** vengono specificati come tipo di ID in un documento XML, questi valori devono essere distinti.</span><span class="sxs-lookup"><span data-stu-id="25863-107">If **CustomerID** and **OrderID** attributes are specified as ID type in an XML document, these values must be distinct.</span></span> <span data-ttu-id="25863-108">In un database, tuttavia, le colonne CustomerID e OrderID possono avere gli stessi valori,</span><span class="sxs-lookup"><span data-stu-id="25863-108">However, in a database, CustomerID and OrderID columns can have the same values.</span></span> <span data-ttu-id="25863-109">ad esempio CustomerID = 1 e OrderID = 1.</span><span class="sxs-lookup"><span data-stu-id="25863-109">(For example, CustomerID = 1 and OrderID = 1 are valid in the database).</span></span>  
  
 <span data-ttu-id="25863-110">Per specificare attributi ID, IDREF e IDREFS validi:</span><span class="sxs-lookup"><span data-stu-id="25863-110">For the ID, IDREF, and IDREFS attributes to be valid:</span></span>  
  
-   <span data-ttu-id="25863-111">Il valore di ID deve essere univoco all'interno del documento XML.</span><span class="sxs-lookup"><span data-stu-id="25863-111">The value of ID must be unique within the XML document.</span></span>  
  
-   <span data-ttu-id="25863-112">Per ogni IDREF e IDREFS, i valori ID di riferimento devono trovarsi nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="25863-112">For every IDREF and IDREFS, the referenced ID values must be in the XML document.</span></span>  
  
-   <span data-ttu-id="25863-113">Il valore di un ID, IDREF e IDREFS deve essere un token denominato.</span><span class="sxs-lookup"><span data-stu-id="25863-113">The value of an ID, IDREF, and IDREFS must be a named token.</span></span> <span data-ttu-id="25863-114">Il valore integer 101, ad esempio, non può essere un valore ID.</span><span class="sxs-lookup"><span data-stu-id="25863-114">(For example, the integer value 101 cannot be an ID value.)</span></span>  
  
-   <span data-ttu-id="25863-115">Non è possibile eseguire il mapping degli attributi di tipo ID, IDREF e IDREFS alle colonne del tipo `text`, `ntext` o `image` o a qualsiasi altro tipo di dati binari, ad esempio `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="25863-115">The attributes of ID, IDREF, and IDREFS type cannot be mapped to columns of the type `text`, `ntext`, or `image` or any other binary data type (for example, `timestamp`).</span></span>  
  
 <span data-ttu-id="25863-116">Se un documento XML contiene più ID, utilizzare l'annotazione `sql:prefix` per assicurarsi che i valori siano univoci.</span><span class="sxs-lookup"><span data-stu-id="25863-116">If an XML document contains multiple IDs, use the `sql:prefix` annotation to ensure that the values are unique.</span></span>  
  
 <span data-ttu-id="25863-117">Notare che l'annotazione `sql:prefix` non può essere utilizzata con un attributo fisso XSD.</span><span class="sxs-lookup"><span data-stu-id="25863-117">Note that `sql:prefix` annotation cannot be used with XSD fixed attribute.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="25863-118">Esempi</span><span class="sxs-lookup"><span data-stu-id="25863-118">Examples</span></span>  
 <span data-ttu-id="25863-119">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="25863-119">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="25863-120">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="25863-120">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-id-and-idrefs-types"></a><span data-ttu-id="25863-121">R.</span><span class="sxs-lookup"><span data-stu-id="25863-121">A.</span></span> <span data-ttu-id="25863-122">Specifica di tipi ID e IDREFS</span><span class="sxs-lookup"><span data-stu-id="25863-122">Specifying ID and IDREFS types</span></span>  
 <span data-ttu-id="25863-123">Nello schema seguente l' **\<Customer>** elemento è costituito dall' **\<Order>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="25863-123">In the following schema, the **\<Customer>** element consists of the **\<Order>** child element.</span></span> <span data-ttu-id="25863-124">L'elemento **\<Order>** include anche un elemento figlio, l' **\<OrderDetail>** elemento.</span><span class="sxs-lookup"><span data-stu-id="25863-124">The **\<Order>** element also has a child element, the **\<OrderDetail>** element.</span></span>  
  
 <span data-ttu-id="25863-125">L'attributo **OrderID** di **\<Customer>** è un attributo di tipo IDREFS che fa riferimento all'attributo **OrderID** dell' **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="25863-125">The **OrderIDList** attribute of **\<Customer>** is an IDREFS type attribute that refers to the **OrderID** attribute of the **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
                 parent="Sales.Customer"  
                 parent-key="CustomerID"  
                 child="Sales.SalesOrderHeader"  
                 child-key="CustomerID" />  
    <sql:relationship name="OrderOrderDetail"  
                 parent="Sales.SalesOrderHeader"  
                 parent-key="SalesOrderID"  
                 child="Sales.SalesOrderDetail"  
                 child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
               sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                   sql:relationship="OrderOrderDetail"   
                   maxOccurs="unbounded" >  
                  <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="ProductID" type="xsd:string" />  
                   <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
               </xsd:element>  
             </xsd:sequence>  
             <xsd:attribute name="SalesOrderID"   
                            type="xsd:ID" sql:prefix="ord-" />  
             <xsd:attribute name="OrderDate" type="xsd:date" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CustomerID" type="xsd:string" />  
    <xsd:attribute name="OrderIDList" type="xsd:IDREFS"   
                   sql:relation="Sales.SalesOrderHeader" sql:field="SalesOrderID"  
                   sql:relationship="CustOrders" sql:prefix="ord-">  
    </xsd:attribute>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="25863-126">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="25863-126">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="25863-127">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="25863-127">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="25863-128">Salvare il file come sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="25863-128">Save the file as sqlPrefix.xml.</span></span>  
  
2.  <span data-ttu-id="25863-129">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="25863-129">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="25863-130">Salvare il file come sqlPrefixT.xml nella stessa directory nella quale è stato salvato sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="25863-130">Save the file as sqlPrefixT.xml in the same directory where you saved sqlPrefix.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="sqlPrefix.xml">  
        /Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="25863-131">Il percorso di directory specificato per lo schema di mapping (sqlPrefix.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="25863-131">The directory path specified for the mapping schema (sqlPrefix.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="25863-132">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="25863-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlPrefix.xml"  
    ```  
  
3.  <span data-ttu-id="25863-133">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="25863-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="25863-134">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="25863-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="25863-135">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="25863-135">This is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" OrderIDList="ord-43860 ord-44501 ord-45283 ord-46042">  
    <Order SalesOrderID="ord-43860" OrderDate="2001-08-01" CustomerID="1">  
      <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
      ...  
    </Order>  
    ...  
 </Customer>  
</ROOT>  
```  
  
  
