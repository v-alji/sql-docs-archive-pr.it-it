---
title: Specifica di uno schema di mapping con annotazioni in un updategram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, updategrams
- data types [SQLXML], mapping schema in updategrams
- updategrams [SQLXML], annotated mapping schemas
- annotated XDR schemas, updategrams
- inverse attribute
- parent-child relationships [SQLXML]
- mapping-schema attribute
- mapping schema [SQLXML], updategrams
- sql:inverse
ms.assetid: 2e266ed9-4cfb-434a-af55-d0839f64bb9a
author: rothja
ms.author: jroth
ms.openlocfilehash: a181b3081b51cca160709703364c248e495e0214
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634949"
---
# <a name="specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-40"></a><span data-ttu-id="9228a-102">Specifica di uno schema di mapping con annotazioni in un updategram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="9228a-102">Specifying an Annotated Mapping Schema in an Updategram (SQLXML 4.0)</span></span>
  <span data-ttu-id="9228a-103">In questo argomento viene illustrata la modalità di utilizzo dello schema di mapping (XSD o XDR) specificato in un updategram per l'elaborazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9228a-103">This topic explains how the mapping schema (XSD or XDR) that is specified in an updategram is used to process the updates.</span></span> <span data-ttu-id="9228a-104">In un updategram è possibile specificare il nome di uno schema di mapping con annotazioni da utilizzare per eseguire il mapping degli elementi e degli attributi nell'updategram alle tabelle e alle colonne in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9228a-104">In an updategram, you can provide the name of an annotated mapping schema to use in mapping the elements and attributes in the updategram to tables and columns in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9228a-105">Quando si specifica uno schema di mapping in un updategram, è necessario eseguire il mapping dei nomi di elemento e di attributo specificati nell'updategram agli elementi e agli attributi dello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="9228a-105">When a mapping schema is specified in an updategram, the element and attribute names that are specified in the updategram must map to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="9228a-106">Per specificare uno schema di mapping, utilizzare l' `mapping-schema` attributo dell' **\<sync>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9228a-106">To specify a mapping schema, you use the `mapping-schema` attribute of the **\<sync>** element.</span></span> <span data-ttu-id="9228a-107">Negli esempi seguenti sono illustrati due updategram, uno che utilizza uno schema di mapping semplice e uno che utilizza uno schema più complesso.</span><span class="sxs-lookup"><span data-stu-id="9228a-107">The following examples show two updategrams: one that uses a simple mapping schema, and one that uses a more complex schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9228a-108">In questa documentazione si presuppone che l'utente disponga di una certa familiarità con i modelli e il supporto dello schema di mapping in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9228a-108">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9228a-109">Per ulteriori informazioni, vedere [Introduzione agli schemi XSD con Annotazioni &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9228a-109">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="9228a-110">Per le applicazioni legacy che usano XDR, vedere la pagina relativa agli [schemi XDR con Annotazioni &#40;deprecati in SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9228a-110">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="dealing-with-data-types"></a><span data-ttu-id="9228a-111">Gestione dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9228a-111">Dealing with Data Types</span></span>  
 <span data-ttu-id="9228a-112">Se lo schema specifica il `image` `binary` `varbinary` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tipo di dati, o (utilizzando `sql:datatype` ) e non specifica un tipo di dati XML, l'updategram presuppone che il tipo di dati XML sia `binary base 64` .</span><span class="sxs-lookup"><span data-stu-id="9228a-112">If the schema specifies the `image`, `binary`, or `varbinary`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (by using `sql:datatype`) and does not specify an XML data type, the updategram assumes that the XML data type is `binary base 64`.</span></span> <span data-ttu-id="9228a-113">Se i dati sono di tipo `bin.base`, è necessario specificare in modo esplicito il tipo (`dt:type=bin.base` o `type="xsd:hexBinary"`).</span><span class="sxs-lookup"><span data-stu-id="9228a-113">If your data is `bin.base` type, you must explicitly specify the type (`dt:type=bin.base` or `type="xsd:hexBinary"`).</span></span>  
  
 <span data-ttu-id="9228a-114">Se lo schema specifica il tipo di dati XSD `dateTime`, `date` o `time`, è necessario specificare anche il tipo di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] corrispondente utilizzando `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="9228a-114">If the schema specifies the `dateTime`, `date`, or `time` XSD data type, you must also specify the corresponding [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type by using `sql:datatype="dateTime"`.</span></span>  
  
 <span data-ttu-id="9228a-115">Quando si gestiscono parametri di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` tipo, è necessario specificare in modo esplicito nel `sql:datatype="money"` nodo appropriato nello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="9228a-115">When handling parameters of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` type, you must explicitly specify `sql:datatype="money"` on the appropriate node in the mapping schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9228a-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="9228a-116">Examples</span></span>  
 <span data-ttu-id="9228a-117">Per creare esempi funzionanti utilizzando gli esempi seguenti, è necessario soddisfare i requisiti specificati nei [requisiti per l'esecuzione di esempi SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="9228a-117">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-creating-an-updategram-with-a-simple-mapping-schema"></a><span data-ttu-id="9228a-118">R.</span><span class="sxs-lookup"><span data-stu-id="9228a-118">A.</span></span> <span data-ttu-id="9228a-119">Creazione di un updategram con uno schema di mapping semplice</span><span class="sxs-lookup"><span data-stu-id="9228a-119">Creating an updategram with a simple mapping schema</span></span>  
 <span data-ttu-id="9228a-120">Lo schema XSD seguente (SampleSchema.xml) è uno schema di mapping che esegue il mapping dell' **\<Customer>** elemento alla tabella Sales. Customer:</span><span class="sxs-lookup"><span data-stu-id="9228a-120">The following XSD schema (SampleSchema.xml) is a mapping schema that maps the **\<Customer>** element to the Sales.Customer table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustID"    
                       sql:field="CustomerID"   
                       type="xsd:string" />  
        <xsd:attribute name="RegionID"    
                       sql:field="TerritoryID"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="9228a-121">L'updategram seguente inserisce un record nella tabella Sales.Customer e si basa sullo schema di mapping precedente per eseguire il mapping di questi dati alla tabella correttamente.</span><span class="sxs-lookup"><span data-stu-id="9228a-121">The following updategram inserts a record into the Sales.Customer table and relies on the previous mapping schema to properly map this data to the table.</span></span> <span data-ttu-id="9228a-122">Si noti che l'updategram utilizza lo stesso nome di elemento, **\<Customer>** , come definito nello schema.</span><span class="sxs-lookup"><span data-stu-id="9228a-122">Notice that the updategram uses the same element name, **\<Customer>**, as defined in the schema.</span></span> <span data-ttu-id="9228a-123">Questa condizione è obbligatoria perché l'updategram specifica uno schema particolare.</span><span class="sxs-lookup"><span data-stu-id="9228a-123">This is mandatory because the updategram specifies a particular schema.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="9228a-124">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="9228a-124">To test the updategram</span></span>  
  
1.  <span data-ttu-id="9228a-125">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="9228a-125">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="9228a-126">Salvare il file come SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="9228a-126">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="9228a-127">Copiare il modello di updategram seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="9228a-127">Copy the updategram template below and paste it into a text file.</span></span> <span data-ttu-id="9228a-128">Salvare il file come SampleUpdategram.xml nella stessa directory nella quale è stato salvato SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="9228a-128">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleUpdateSchema.xml">  
        <updg:before>  
          <Customer CustID="1" RegionID="1"  />  
        </updg:before>  
        <updg:after>  
          <Customer CustID="1" RegionID="2" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="9228a-129">Il percorso di directory specificato per lo schema di mapping (SampleUpdateSchema.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="9228a-129">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="9228a-130">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9228a-130">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="9228a-131">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="9228a-131">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="9228a-132">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9228a-132">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="9228a-133">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="9228a-133">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Customer" sql:relation="Sales.Customer" >  
       <AttributeType name="CustID" />  
       <AttributeType name="RegionID" />  
  
       <attribute type="CustID" sql:field="CustomerID" />  
       <attribute type="RegionID" sql:field="TerritoryID" />  
     </ElementType>  
   </Schema>   
```  
  
### <a name="b-inserting-a-record-by-using-the-parent-child-relationship-specified-in-the-mapping-schema"></a><span data-ttu-id="9228a-134">B.</span><span class="sxs-lookup"><span data-stu-id="9228a-134">B.</span></span> <span data-ttu-id="9228a-135">Inserimento di un record tramite la relazione padre-figlio specificata nello schema di mapping</span><span class="sxs-lookup"><span data-stu-id="9228a-135">Inserting a record by using the parent-child relationship specified in the mapping schema</span></span>  
 <span data-ttu-id="9228a-136">Gli elementi dello schema possono essere correlati.</span><span class="sxs-lookup"><span data-stu-id="9228a-136">Schema elements can be related.</span></span> <span data-ttu-id="9228a-137">L' **\<sql:relationship>** elemento specifica la relazione padre-figlio tra gli elementi dello schema.</span><span class="sxs-lookup"><span data-stu-id="9228a-137">The **\<sql:relationship>** element specifies the parent-child relationship between the schema elements.</span></span> <span data-ttu-id="9228a-138">Queste informazioni vengono utilizzate per aggiornare le tabelle corrispondenti che presentano una relazione chiave primaria/chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="9228a-138">This information is used to update corresponding tables that have primary-key/foreign-key relationship.</span></span>  
  
 <span data-ttu-id="9228a-139">Lo schema di mapping seguente (SampleSchema.xml) è costituito da due elementi **\<Order>** **\<OD>** :</span><span class="sxs-lookup"><span data-stu-id="9228a-139">The following mapping schema (SampleSchema.xml) consists of two elements, **\<Order>** and **\<OD>**:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="OD"   
                     sql:relation="Sales.SalesOrderDetail"  
                     sql:relationship="OrderOD" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID"   type="xsd:integer" />  
              <xsd:attribute name="ProductID" type="xsd:integer" />  
             <xsd:attribute name="UnitPrice"  type="xsd:decimal" />  
             <xsd:attribute name="OrderQty"   type="xsd:integer" />  
             <xsd:attribute name="UnitPriceDiscount"   type="xsd:decimal" />  
  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesOrderID"  type="xsd:integer" />  
        <xsd:attribute name="OrderDate"  type="xsd:date" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="9228a-140">L'updategram seguente utilizza questo schema XSD per aggiungere un nuovo record di dettagli dell'ordine (un **\<OD>** elemento nel **\<after>** blocco) per l'ordine 43860.</span><span class="sxs-lookup"><span data-stu-id="9228a-140">The following updategram uses this XSD schema to add a new order detail record (an **\<OD>** element in the **\<after>** block) for order 43860.</span></span> <span data-ttu-id="9228a-141">L'attributo `mapping-schema` viene utilizzato per specificare lo schema di mapping nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="9228a-141">The `mapping-schema` attribute is used to specify the mapping schema in the updategram.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43860" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43860" >  
           <OD ProductID="753" UnitPrice="$10.00"  
               Quantity="5" Discount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="9228a-142">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="9228a-142">To test the updategram</span></span>  
  
1.  <span data-ttu-id="9228a-143">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="9228a-143">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="9228a-144">Salvare il file come SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="9228a-144">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="9228a-145">Copiare il modello di updategram precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="9228a-145">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="9228a-146">Salvare il file come SampleUpdategram.xml nella stessa directory nella quale è stato salvato SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="9228a-146">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="9228a-147">Il percorso di directory specificato per lo schema di mapping (SampleUpdateSchema.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="9228a-147">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="9228a-148">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9228a-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="9228a-149">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="9228a-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="9228a-150">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9228a-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="9228a-151">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="9228a-151">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="OD" sql:relation="Sales.SalesOrderDetail" >  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="ProductID" />  
    <AttributeType name="UnitPrice"  dt:type="fixed.14.4" />  
    <AttributeType name="OrderQty" />  
    <AttributeType name="UnitPriceDiscount" />  
  
    <attribute type="SalesOrderID" />  
    <attribute type="ProductID" />  
    <attribute type="UnitPrice" />  
    <attribute type="OrderQty" />  
    <attribute type="UnitPriceDiscount" />  
</ElementType>  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="OrderDate" />  
  
    <attribute type="CustomerID" />  
    <attribute type="SalesOrderID" />  
    <attribute type="OrderDate" />  
    <element type="OD" >  
             <sql:relationship   
                   key-relation="Sales.SalesOrderHeader"  
                   key="SalesOrderID"  
                   foreign-key="SalesOrderID"  
                   foreign-relation="Sales.SalesOrderDetail" />  
    </element>  
</ElementType>  
</Schema>  
```  
  
### <a name="c-inserting-a-record-by-using-the-parent-child-relationship-and-inverse-annotation-specified-in-the-xsd-schema"></a><span data-ttu-id="9228a-152">C.</span><span class="sxs-lookup"><span data-stu-id="9228a-152">C.</span></span> <span data-ttu-id="9228a-153">Inserimento di un record tramite la relazione padre-figlio e l'annotazione inverse specificata nello schema XSD</span><span class="sxs-lookup"><span data-stu-id="9228a-153">Inserting a record by using the parent-child relationship and inverse annotation specified in the XSD schema</span></span>  
 <span data-ttu-id="9228a-154">In questo esempio viene illustrato in che modo la logica dell'updategram utilizza la relazione padre-figlio specificata in XSD per elaborare gli aggiornamenti e viene descritta la modalità di utilizzo dell'annotazione `inverse`.</span><span class="sxs-lookup"><span data-stu-id="9228a-154">This example illustrates how the updategram logic uses the parent-child relationship specified in the XSD to process updates, and how the `inverse` annotation is used.</span></span> <span data-ttu-id="9228a-155">Per ulteriori informazioni sull' `inverse` annotazione, vedere [specifica dell'attributo SQL: inverse in SQL: Relationship &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9228a-155">For more information about the `inverse` annotation, see [Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="9228a-156">In questo esempio si presuppone che le tabelle seguenti si trovino nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="9228a-156">This example assumes that the following tables are in the **tempdb** database:</span></span>  
  
-   <span data-ttu-id="9228a-157">`Cust (CustomerID, CompanyName)`, dove `CustomerID` è la chiave primaria</span><span class="sxs-lookup"><span data-stu-id="9228a-157">`Cust (CustomerID, CompanyName)`, where `CustomerID` is the primary key</span></span>  
  
-   <span data-ttu-id="9228a-158">`Ord (OrderID, CustomerID)`, dove `CustomerID` è una chiave esterna che fa riferimento alla chiave primaria `CustomerID` nella tabella `Cust`.</span><span class="sxs-lookup"><span data-stu-id="9228a-158">`Ord (OrderID, CustomerID)`, where `CustomerID` is a foreign key that refers to the `CustomerID` primary key in the `Cust` table.</span></span>  
  
 <span data-ttu-id="9228a-159">L'updategram utilizza lo schema XSD seguente per inserire i record nelle tabelle Cust e Ord:</span><span class="sxs-lookup"><span data-stu-id="9228a-159">The updategram uses the following XSD schema to insert records into the Cust and Ord tables :</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
       <sql:relationship name="OrdCust" inverse="true"  
                  parent="Ord"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Cust"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
<xsd:element name="Order" sql:relation="Ord">  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customer" sql:relationship="OrdCust"/>  
    </xsd:sequence>  
    <xsd:attribute name="OrderID"   type="xsd:int"/>  
    <xsd:attribute name="CustomerID" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
<xsd:element name="Customer" sql:relation="Cust">  
  <xsd:complexType>  
     <xsd:attribute name="CustomerID"  type="xsd:string"/>  
    <xsd:attribute name="CompanyName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="9228a-160">Lo schema XSD in questo esempio include **\<Customer>** **\<Order>** gli elementi e e specifica una relazione padre-figlio tra i due elementi.</span><span class="sxs-lookup"><span data-stu-id="9228a-160">The XSD schema in this example has **\<Customer>** and **\<Order>** elements, and it specifies a parent-child relationship between the two elements.</span></span> <span data-ttu-id="9228a-161">Identifica **\<Order>** come elemento padre e **\<Customer>** come elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="9228a-161">It identifies **\<Order>** as the parent element and **\<Customer>** as the child element.</span></span>  
  
 <span data-ttu-id="9228a-162">La logica di elaborazione dell'updategram utilizza le informazioni sulla relazione padre-figlio per determinare l'ordine in cui i record vengono inseriti nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="9228a-162">The updategram processing logic uses the information about the parent-child relationship to determine the order in which records are inserted into tables.</span></span> <span data-ttu-id="9228a-163">In questo esempio, la logica dell'updategram tenta innanzitutto di inserire un record nella tabella Ord (perché **\<Order>** è l'elemento padre), quindi tenta di inserire un record nella tabella Cust (perché **\<Customer>** è l'elemento figlio).</span><span class="sxs-lookup"><span data-stu-id="9228a-163">In this example, the updategram logic first attempts to insert a record into the Ord table (because **\<Order>** is the parent) and then attempts to insert a record into the Cust table (because **\<Customer>** is the child).</span></span> <span data-ttu-id="9228a-164">A causa delle informazioni su chiave primaria/chiave esterna contenute nello schema della tabella di database, questa operazione di inserimento genera tuttavia una violazione di chiave esterna nel database e pertanto l'inserimento ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9228a-164">However, because of the primary key/foreign key information that is contained in the database table schema, this insert operation causes a foreign key violation in the database and the insert fails.</span></span>  
  
 <span data-ttu-id="9228a-165">Per indicare alla logica dell'updategram di invertire la relazione padre-figlio durante l'operazione di aggiornamento, l' `inverse` annotazione viene specificata nell' **\<relationship>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9228a-165">To instruct the updategram logic to reverse the parent-child relationship during the update operation, the `inverse` annotation is specified on the **\<relationship>** element.</span></span> <span data-ttu-id="9228a-166">Di conseguenza, i record vengono aggiunti prima nella tabella Cust e successivamente nella tabella Ord e l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="9228a-166">As a result, records are added first in the Cust table and then in the Ord table, and the operation succeeds.</span></span>  
  
 <span data-ttu-id="9228a-167">Nell'updategram seguente viene inserito un ordine (OrderID=2) nella tabella Ord e un cliente (CustomerID='AAAAA) nella tabella Cust tramite lo schema XSD specificato:</span><span class="sxs-lookup"><span data-stu-id="9228a-167">The following updategram inserts an order (OrderID=2) in the Ord table and a customer (CustomerID='AAAAA') in the Cust table by using the specified XSD schema:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before/>  
    <updg:after>  
      <Order OrderID="2" CustomerID="AAAAA" >  
        <Customer CustomerID="AAAAA" CompanyName="AAAAA Company" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="9228a-168">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="9228a-168">To test the updategram</span></span>  
  
1.  <span data-ttu-id="9228a-169">Creare le tabelle seguenti nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="9228a-169">Create these tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust(CustomerID varchar(5) primary key,   
                      CompanyName varchar(20))  
    GO  
    CREATE TABLE Ord (OrderID int primary key,   
                      CustomerID varchar(5) references Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="9228a-170">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="9228a-170">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="9228a-171">Salvare il file come SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="9228a-171">Save the file as SampleUpdateSchema.xml.</span></span>  
  
3.  <span data-ttu-id="9228a-172">Copiare il modello di updategram precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="9228a-172">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="9228a-173">Salvare il file come SampleUpdategram.xml nella stessa directory nella quale è stato salvato SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="9228a-173">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="9228a-174">Il percorso di directory specificato per lo schema di mapping (SampleUpdateSchema.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="9228a-174">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="9228a-175">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9228a-175">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
4.  <span data-ttu-id="9228a-176">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="9228a-176">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="9228a-177">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9228a-177">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9228a-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9228a-178">See Also</span></span>  
 [<span data-ttu-id="9228a-179">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9228a-179">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
