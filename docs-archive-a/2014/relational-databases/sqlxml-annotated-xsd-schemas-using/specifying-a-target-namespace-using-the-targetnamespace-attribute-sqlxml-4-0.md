---
title: Specifica di uno spazio dei nomi di destinazione mediante l'attributo targetNamespace (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- targetNamespace attribute
- XSD schemas [SQLXML], target namespaces
- annotated XSD schemas, target namespaces
- xsd:targetNamespace
- attributeFormDefault attribute
- elementFormDefault attribute
- target namespaces [SQLXML]
ms.assetid: f3df9877-6672-4444-8245-2670063c9310
author: rothja
ms.author: jroth
ms.openlocfilehash: 823bcbf7f4906a2e1d2ced1ff58b681c0ca41a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636635"
---
# <a name="specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-40"></a><span data-ttu-id="ca2d6-102">Specifica di uno spazio dei nomi di destinazione mediante l'attributo targetNamespace (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ca2d6-102">Specifying a Target Namespace Using the targetNamespace Attribute (SQLXML 4.0)</span></span>
  <span data-ttu-id="ca2d6-103">Per la scrittura di schemi XSD, è possibile utilizzare l'attributo **TARGETNAMESPACE** XSD per specificare uno spazio dei nomi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-103">In writing XSD schemas, you can use the XSD **targetNamespace** attribute to specify a target namespace.</span></span> <span data-ttu-id="ca2d6-104">In questo argomento viene descritto il funzionamento degli attributi XSD **targetNamespace**, **elementFormDefault**e **attributeFormDefault** , il modo in cui influiscono sull'istanza XML generata e come vengono specificate le query XPath con gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-104">This topic describes how the XSD **targetNamespace**, **elementFormDefault**, and **attributeFormDefault** attributes work, how they affect the XML instance that is generated, and how XPath queries are specified with namespaces.</span></span>  
  
 <span data-ttu-id="ca2d6-105">È possibile utilizzare l'attributo **xsd: targetNamespace** per inserire gli elementi e gli attributi dello spazio dei nomi predefinito in uno spazio dei nomi diverso.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-105">You can use the **xsd:targetNamespace** attribute to place elements and attributes from the default namespace into a different namespace.</span></span> <span data-ttu-id="ca2d6-106">È inoltre possibile specificare se gli elementi e gli attributi dello schema dichiarati localmente devono essere qualificati da uno spazio dei nomi, sia in modo esplicito mediante un prefisso sia in modo implicito per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-106">You can also specify whether the locally declared elements and attributes of the schema should appear qualified by a namespace, either explicitly by using a prefix or implicitly by default.</span></span> <span data-ttu-id="ca2d6-107">È possibile usare gli attributi **elementFormDefault** e **attributeFormDefault** sull' **\<xsd:schema>** elemento per specificare a livello globale la qualificazione di elementi e attributi locali oppure è possibile usare l'attributo **form** per specificare separatamente i singoli elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-107">You can use the **elementFormDefault** and **attributeFormDefault** attributes on the **\<xsd:schema>** element to globally specify the qualification of local elements and attributes, or you can use the **form** attribute to specify individual elements and attributes separately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ca2d6-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="ca2d6-108">Examples</span></span>  
 <span data-ttu-id="ca2d6-109">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="ca2d6-110">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="ca2d6-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-a-target-namespace"></a><span data-ttu-id="ca2d6-111">R.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-111">A.</span></span> <span data-ttu-id="ca2d6-112">Specificare uno spazio dei nomi di destinazione</span><span class="sxs-lookup"><span data-stu-id="ca2d6-112">Specifying a target namespace</span></span>  
 <span data-ttu-id="ca2d6-113">Nello schema XSD seguente viene specificato uno spazio dei nomi di destinazione utilizzando l'attributo **xsd: targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="ca2d6-113">The following XSD schema specifies a target namespace by using the **xsd:targetNamespace** attribute.</span></span> <span data-ttu-id="ca2d6-114">Lo schema imposta anche i valori degli attributi **elementFormDefault** e **attributeFormDefault** su **"unqualified"** (il valore predefinito per questi attributi).</span><span class="sxs-lookup"><span data-stu-id="ca2d6-114">The schema also sets the **elementFormDefault** and **attributeFormDefault** attribute values to **"unqualified"** (the default value for these attributes).</span></span> <span data-ttu-id="ca2d6-115">Si tratta di una dichiarazione globale che interessa tutti gli elementi locali ( **\<Order>** nello schema) e gli attributi (**CustomerID**, **ContactName**e **OrderID** nello schema).</span><span class="sxs-lookup"><span data-stu-id="ca2d6-115">This is a global declaration and affects all the local elements (**\<Order>** in the schema) and attributes (**CustomerID**, **ContactName**, and **OrderID** in the schema).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:CO="urn:MyNamespace"   
            targetNamespace="urn:MyNamespace" >  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer"   
               sql:relation="Sales.Customer"   
               type="CO:CustomerType" />  
  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustOrders"  
                     type="CO:OrderType" />  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesPersonID"  type="xsd:string" />  
  </xsd:complexType>  
  <xsd:complexType name="OrderType" >  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="ca2d6-116">Nello schema:</span><span class="sxs-lookup"><span data-stu-id="ca2d6-116">In the schema:</span></span>  
  
-   <span data-ttu-id="ca2d6-117">Le dichiarazioni di tipo **CustomerType** e **OrderType** sono globali e, pertanto, sono incluse nello spazio dei nomi di destinazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-117">The **CustomerType** and **OrderType** type declarations are global and, therefore, are included in the schema's target namespace.</span></span> <span data-ttu-id="ca2d6-118">Di conseguenza, quando a questi tipi viene fatto riferimento nella dichiarazione dell' **\<Customer>** elemento e del relativo **\<Order>** elemento figlio, viene specificato un prefisso associato allo spazio dei nomi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-118">As a result, when these types are referenced in the declaration of **\<Customer>** element and its **\<Order>** child element, a prefix is specified that is associated with the target namespace.</span></span>  
  
-   <span data-ttu-id="ca2d6-119">L' **\<Customer>** elemento viene inoltre incluso nello spazio dei nomi di destinazione dello schema poiché è un elemento globale nello schema.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-119">The **\<Customer>** element is also included in the target namespace of the schema because it is a global element in the schema.</span></span>  
  
 <span data-ttu-id="ca2d6-120">Eseguire sullo schema la query Xpath seguente:</span><span class="sxs-lookup"><span data-stu-id="ca2d6-120">Execute the following XPath query against the schema:</span></span>  
  
```  
(/CO:Customer[@CustomerID=1)   
```  
  
 <span data-ttu-id="ca2d6-121">La query XPath genera questo documento dell'istanza (sono mostrati solo alcuni ordini):</span><span class="sxs-lookup"><span data-stu-id="ca2d6-121">The XPath query generates this instance document (only a few of the orders are shown):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <y0:Customer xmlns:y0="urn:MyNamespace"   
      CustomerID="ALFKI" ContactName="Maria Anders">  
        <Order CustomerID="ALFKI" OrderID="10643" />   
        <Order CustomerID="ALFKI" OrderID="10692" />   
        ...  
  </y0:Customer>  
  </ROOT>  
```  
  
 <span data-ttu-id="ca2d6-122">Questo documento di istanza definisce lo spazio dei nomi urn: MyNamespace e vi associa un prefisso (y0).</span><span class="sxs-lookup"><span data-stu-id="ca2d6-122">This instance document defines the urn:MyNamespace namespace and associates a prefix (y0) to it.</span></span> <span data-ttu-id="ca2d6-123">Il prefisso viene applicato solo all' **\<Customer>** elemento globale.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-123">The prefix is applied only to the **\<Customer>** global element.</span></span> <span data-ttu-id="ca2d6-124">L'elemento è globale perché è dichiarato come elemento figlio dell' **\<xsd:schema>** elemento nello schema.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-124">(The element is global because it is declared as a child of **\<xsd:schema>** element in the schema.)</span></span>  
  
 <span data-ttu-id="ca2d6-125">Il prefisso non viene applicato agli elementi e agli attributi locali poiché il valore degli attributi **elementFormDefault** e **attributeFormDefault** è impostato su **"unqualified"** nello schema.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-125">The prefix is not applied to the local elements and attributes because the value of **elementFormDefault** and **attributeFormDefault** attributes is set to **"unqualified"** in the schema.</span></span> <span data-ttu-id="ca2d6-126">Si noti che l' **\<Order>** elemento è locale perché la relativa dichiarazione appare come elemento figlio dell' **\<complexType>** elemento che definisce l' **\<CustomerType>** elemento.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-126">Note that the **\<Order>** element is local because its declaration appears as a child of the **\<complexType>** element that defines the **\<CustomerType>** element.</span></span> <span data-ttu-id="ca2d6-127">Analogamente, gli attributi (**CustomerID**, **OrderID**e **ContactName**) sono locali e non globali.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-127">Similarly, the attributes (**CustomerID**, **OrderID**, and **ContactName**) are local, not global.</span></span>  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="ca2d6-128">Per creare un esempio reale di questo schema</span><span class="sxs-lookup"><span data-stu-id="ca2d6-128">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="ca2d6-129">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="ca2d6-130">Salvare il file con il nome targetNameSpace.xml.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-130">Save the file as targetNameSpace.xml.</span></span>  
  
2.  <span data-ttu-id="ca2d6-131">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-131">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="ca2d6-132">Salvare il file come targetNameSpaceT.xml nella stessa directory nella quale è stato salvato targetNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-132">Save the file as targetNameSpaceT.xml in the same directory where you saved targetNamespace.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="targetNamespace.xml"  
                       xmlns:CO="urn:MyNamespace" >  
        /CO:Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="ca2d6-133">La query XPath nel modello restituisce l' **\<Customer>** elemento per il cliente con CustomerID 1.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-133">The XPath query in the template returns the **\<Customer>** element for the customer with a CustomerID of 1.</span></span> <span data-ttu-id="ca2d6-134">Notare che la query XPath specifica il prefisso dello spazio dei nomi per l'elemento nella query e non per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-134">Note that the XPath query specifies the namespace prefix for the element in the query and not for the attribute.</span></span> <span data-ttu-id="ca2d6-135">Gli attributi locali non sono qualificati, come specificato nello schema.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-135">(Local attributes are not qualified, as specified in the schema.)</span></span>  
  
     <span data-ttu-id="ca2d6-136">Il percorso di directory specificato per lo schema di mapping (targetNamespace.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-136">The directory path specified for the mapping schema (targetNamespace.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="ca2d6-137">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ca2d6-137">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\targetNamepsace.xml"  
    ```  
  
3.  <span data-ttu-id="ca2d6-138">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-138">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="ca2d6-139">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ca2d6-139">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="ca2d6-140">Se lo schema specifica gli attributi **elementFormDefault** e **attributeFormDefault** con il valore **"qualified"**, il documento dell'istanza disporrà di tutti gli elementi e gli attributi locali qualificati.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-140">If the schema specifies **elementFormDefault** and **attributeFormDefault** attributes with value **"qualified"**, the instance document will have all of the local elements and attributes qualified.</span></span> <span data-ttu-id="ca2d6-141">È possibile modificare lo schema precedente in modo da includere questi attributi nell' **\<xsd:schema>** elemento ed eseguire nuovamente il modello.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-141">You can change the previous schema to include these attributes in the **\<xsd:schema>** element and execute the template again.</span></span> <span data-ttu-id="ca2d6-142">Poiché ora anche gli attributi sono qualificati nell'istanza, la query XPath verrà modificata per includere il prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ca2d6-142">Because the attributes are now also qualified in the instance, the XPath query will change to include the namespace prefix.</span></span>  
  
 <span data-ttu-id="ca2d6-143">La query XPath modificata è:</span><span class="sxs-lookup"><span data-stu-id="ca2d6-143">This is the revised XPath query:</span></span>  
  
```  
/CO:Customer[@CO:CustomerID=1]  
```  
  
 <span data-ttu-id="ca2d6-144">Di seguito è riportato il documento XML restituito:</span><span class="sxs-lookup"><span data-stu-id="ca2d6-144">This is the XML document that is returned:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <y0:Customer xmlns:y0="urn:MyNamespace" CustomerID="1" SalesPersonID="280">  
      <Order SalesOrderID="43860" CustomerID="1" />   
      <Order SalesOrderID="44501" CustomerID="1" />   
      <Order SalesOrderID="45283" CustomerID="1" />   
      <Order SalesOrderID="46042" CustomerID="1" />   
   </y0:Customer>  
</ROOT>  
```  
  
  
