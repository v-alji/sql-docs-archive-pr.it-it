---
title: 'Creazione di elementi costanti tramite SQL: is-constant (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- sql:is-constant
- XSD schemas [SQLXML], constant elements
- element mapping [SQLXML], constant elements
- is-constant annotation
- constant elements [SQLXML]
- annotated XSD schemas, constant elements
ms.assetid: 940eea1b-54f5-445f-b844-c894d9f3941b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8deedd8547d6bc3f0154eedb889ad908750f071a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717627"
---
# <a name="creating-constant-elements-using-sqlis-constant-sqlxml-40"></a><span data-ttu-id="09f17-102">Creazione di elementi costanti tramite sql:is-constant (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="09f17-102">Creating Constant Elements Using sql:is-constant (SQLXML 4.0)</span></span>
  <span data-ttu-id="09f17-103">Per specificare un elemento costante, ovvero un elemento nello schema XSD che non esegue il mapping ad alcuna tabella o colonna di database, è possibile utilizzare l' `sql:is-constant` annotazione.</span><span class="sxs-lookup"><span data-stu-id="09f17-103">To specify a constant element-that is, an element in the XSD schema that does not map to any database table or column-you can use the `sql:is-constant` annotation.</span></span> <span data-ttu-id="09f17-104">Questa annotazione accetta un valore booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="09f17-104">This annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="09f17-105">I valori possibili sono 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="09f17-105">The acceptable values are 0, 1, true, and false.</span></span> <span data-ttu-id="09f17-106">L'annotazione `sql:is-constant` può essere specificata in un elemento che non include alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="09f17-106">The `sql:is-constant` annotation can be specified on an element that does not have any attributes.</span></span> <span data-ttu-id="09f17-107">Se viene specificata in un elemento con valore true (o 1), l'elemento non viene mappato al database ma viene comunque visualizzato nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="09f17-107">If it is specified on an element with the value true (or 1), that element is not mapped to the database but still appears in the XML document.</span></span>  
  
 <span data-ttu-id="09f17-108">È possibile utilizzare l'annotazione `sql:is-constant` per le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="09f17-108">The `sql:is-constant` annotation can be used for:</span></span>  
  
-   <span data-ttu-id="09f17-109">Aggiunta di un elemento di livello principale al documento XML.</span><span class="sxs-lookup"><span data-stu-id="09f17-109">Adding a top-level element to the XML document.</span></span> <span data-ttu-id="09f17-110">XML richiede un singolo elemento di livello principale (elemento radice) per il documento.</span><span class="sxs-lookup"><span data-stu-id="09f17-110">XML requires a single top-level element (root element) for the document.</span></span>  
  
-   <span data-ttu-id="09f17-111">Creazione di elementi contenitore, ad esempio un **\<Orders>** elemento che esegue il wrapping di tutti gli ordini.</span><span class="sxs-lookup"><span data-stu-id="09f17-111">Creating container elements, such as an **\<Orders>** element that wraps all orders.</span></span>  
  
 <span data-ttu-id="09f17-112">L' `sql:is-constant` annotazione può essere aggiunta a un **\<complexType>** elemento.</span><span class="sxs-lookup"><span data-stu-id="09f17-112">The `sql:is-constant` annotation can be added to a **\<complexType>** element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="09f17-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="09f17-113">Examples</span></span>  
 <span data-ttu-id="09f17-114">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="09f17-114">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="09f17-115">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="09f17-115">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlis-constant-to-add-a-container-element"></a><span data-ttu-id="09f17-116">R.</span><span class="sxs-lookup"><span data-stu-id="09f17-116">A.</span></span> <span data-ttu-id="09f17-117">Definizione di sql:is-constant per aggiungere un elemento contenitore</span><span class="sxs-lookup"><span data-stu-id="09f17-117">Specifying sql:is-constant to add a container element</span></span>  
 <span data-ttu-id="09f17-118">In questo schema XSD con annotazioni, **\<CustomerOrders>** viene definito come elemento costante specificando l' `sql:is-constant` attributo con un valore pari a 1.</span><span class="sxs-lookup"><span data-stu-id="09f17-118">In this annotated XSD schema, **\<CustomerOrders>** is defined as a constant element by specifying the `sql:is-constant` attribute with a value of 1.</span></span> <span data-ttu-id="09f17-119">Pertanto, **\<CustomerOrders>** non è mappato ad alcuna tabella o colonna di database.</span><span class="sxs-lookup"><span data-stu-id="09f17-119">Therefore, **\<CustomerOrders>** is not mapped to any database table or column.</span></span> <span data-ttu-id="09f17-120">Questo elemento costante è costituito dagli **\<Order>** elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="09f17-120">This constant element consists of the **\<Order>** child elements.</span></span>  
  
 <span data-ttu-id="09f17-121">Sebbene non sia **\<CustomerOrders>** mappato ad alcuna tabella o colonna di database, viene comunque visualizzato nel codice XML risultante come elemento contenitore contenente gli **\<Order>** elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="09f17-121">Although **\<CustomerOrders>** does not map to any database table or column, it still appears in the resulting XML as a container element containing the **\<Order>** child elements.</span></span>  
  
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
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="CustomerOrders" sql:is-constant="1" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"  
                           sql:relationship="CustOrders"   
                           maxOccurs="unbounded" >  
                <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="OrderDate" type="xsd:date" />  
                   <xsd:attribute name="CustomerID" type="xsd:string" />  
                </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>  
         </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="09f17-122">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="09f17-122">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="09f17-123">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="09f17-123">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="09f17-124">Salvare il file con il nome isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="09f17-124">Save the file as isConstant.xml.</span></span>  
  
2.  <span data-ttu-id="09f17-125">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="09f17-125">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="09f17-126">Salvare il file con il nome isConstantT.xml nella stessa directory in cui è stato salvato il file isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="09f17-126">Save the file as isConstantT.xml in the same directory where you saved isConstant.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="isConstant.xml">  
            Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="09f17-127">Il percorso di directory specificato per lo schema di mapping (isConstant.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="09f17-127">The directory path specified for the mapping schema (isConstant.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="09f17-128">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09f17-128">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\isConstant.xml"  
    ```  
  
3.  <span data-ttu-id="09f17-129">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="09f17-129">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="09f17-130">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="09f17-130">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="09f17-131">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="09f17-131">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
<Customer CustomerID="1">   
  <CustomerOrders>   
    <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1" />   
    <Order SalesOrderID="44501" OrderDate="2001-11-01" CustomerID="1" />   
    <Order SalesOrderID="45283" OrderDate="2002-02-01" CustomerID="1" />   
    <Order SalesOrderID="46042" OrderDate="2002-05-01" CustomerID="1" />   
    ...  
  </CustomerOrders>   
</Customer>   
</ROOT>  
```  
  
  
