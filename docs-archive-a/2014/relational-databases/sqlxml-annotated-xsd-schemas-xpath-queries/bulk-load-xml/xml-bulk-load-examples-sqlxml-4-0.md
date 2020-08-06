---
title: Esempi di caricamento bulk XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- ConnectionCommand property
- XMLFragment property
- relationship chains [SQLXML]
- multiple table bulk loading
- examples [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:datatype
- transaction mode [SQLXML]
- CheckConstraints property
- sql:overflow-field
- XML Bulk Load [SQLXML], examples
- TempFilePath property
- datatype annotation
- Transaction property
- KeepIdentity property
- Execute method
- streaming XML data
- xml data type [SQL Server], SQLXML
- bulk load [SQLXML], examples
ms.assetid: 970e4553-b41d-4a12-ad50-0ee65d1f305d
author: rothja
ms.author: jroth
ms.openlocfilehash: c7eaec77ef068efd28c4da65833afa5047b222f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711808"
---
# <a name="xml-bulk-load-examples-sqlxml-40"></a><span data-ttu-id="8d8cd-102">Esempi di caricamento bulk XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="8d8cd-102">XML Bulk Load Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="8d8cd-103">Negli esempi seguenti viene illustrata la funzionalità di caricamento bulk XML in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d8cd-103">The following examples illustrate the XML Bulk Load functionality in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8d8cd-104">In ogni esempio vengono forniti uno schema XSD e lo schema XDR equivalente.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-104">Each example provides an XSD schema and its equivalent XDR schema.</span></span>  
  
## <a name="bulk-loader-script-validateandbulkloadvbs"></a><span data-ttu-id="8d8cd-105">Script per il caricamento bulk (ValidateAndBulkload.vbs)</span><span class="sxs-lookup"><span data-stu-id="8d8cd-105">Bulk Loader Script (ValidateAndBulkload.vbs)</span></span>  
 <span data-ttu-id="8d8cd-106">Lo script seguente, scritto in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), carica un documento XML nel DOM XML; lo convalida rispetto a uno schema e, se il documento è valido, esegue un caricamento bulk XML per caricare il codice XML in una [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabella.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-106">The following script, written in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), loads an XML document into the XML DOM; validates it against a schema; and, if the document is valid, executes an XML bulk load to load the XML into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="8d8cd-107">Lo script può essere utilizzato con ognuno dei singoli esempi che vi fanno riferimento più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-107">This script can be used with each of the individual examples that refer to it later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d8cd-108">Il caricamento bulk XML non genera un avviso o un errore se non viene caricato alcun contenuto dal file di dati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-108">XML Bulk Load does not throw a warning or an error if no content is uploaded from the data file.</span></span> <span data-ttu-id="8d8cd-109">È pertanto consigliabile convalidare il file di dati XML prima di eseguire un'operazione di caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-109">Therefore, it is a good practice to validate your XML data file prior to executing a bulk load operation.</span></span>  
  
```  
Dim FileValid  
  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
'Validate the data file prior to bulkload  
Dim sOutput   
sOutput = ValidateFile("SampleXMLData.xml", "", "SampleSchema.xml")  
WScript.Echo sOutput  
  
If FileValid Then  
   ' Check constraints and initiate transaction (if needed)  
   ' objBL.CheckConstraints = True  
   ' objBL.Transaction=True  
  'Execute XML bulkload using file.  
  objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
  set objBL=Nothing  
End If  
  
Function ValidateFile(strXmlFile,strUrn,strXsdFile)  
  
   ' Create a schema cache and add SampleSchema.xml to it.  
   Dim xs, fso, sAppPath  
   Set fso = CreateObject("Scripting.FileSystemObject")   
   Set xs = CreateObject("MSXML2.XMLSchemaCache.6.0")  
   sAppPath = fso.GetFolder(".")   
   xs.Add strUrn, sAppPath & "\" & strXsdFile  
  
   ' Create an XML DOMDocument object.  
   Dim xd   
   Set xd = CreateObject("MSXML2.DOMDocument.6.0")  
  
   ' Assign the schema cache to the DOM document.  
   ' schemas collection.  
   Set xd.schemas = xs  
  
   ' Load XML document as DOM document.  
   xd.async = False  
   xd.Load sAppPath & "\" & strXmlFile  
  
   ' Return validation results in message to the user.  
   If xd.parseError.errorCode <> 0 Then  
        ValidateFile = "Validation failed on " & _  
             strXmlFile & vbCrLf & _  
             "=======" & vbCrLf & _  
             "Reason: " & xd.parseError.reason & _  
             vbCrLf & "Source: " & _  
             xd.parseError.srcText & _  
             vbCrLf & "Line: " & _  
             xd.parseError.Line & vbCrLf  
             FileValid = False  
    Else  
        ValidateFile = "Validation succeeded for " & _  
             strXmlFile & vbCrLf & _  
             "========" & _  
             vbCrLf & "Contents to be bulkloaded" & vbCrLf  
             FileValid = True  
    End If  
End Function  
```  
  
## <a name="a-bulk-loading-xml-in-a-table"></a><span data-ttu-id="8d8cd-110">R.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-110">A.</span></span> <span data-ttu-id="8d8cd-111">Caricamento bulk di un file XML in una tabella</span><span class="sxs-lookup"><span data-stu-id="8d8cd-111">Bulk loading XML in a table</span></span>  
 <span data-ttu-id="8d8cd-112">In questo esempio viene stabilita una connessione all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specificata nella proprietà ConnectionString (MyServer).</span><span class="sxs-lookup"><span data-stu-id="8d8cd-112">This example establishes a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is specified in the ConnectionString property (MyServer).</span></span> <span data-ttu-id="8d8cd-113">Nell'esempio viene inoltre specificata la Proprietà ErrorLogFile.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-113">The example also specifies the ErrorLogFile property.</span></span> <span data-ttu-id="8d8cd-114">L'output degli errori viene pertanto salvato nel file specificato ("C:\error.log"), che può essere anche spostato in un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-114">Therefore, the error output is saved in the specified file ("C:\error.log"), which you might also decide to change to a different location.</span></span> <span data-ttu-id="8d8cd-115">Si noti inoltre che il metodo Execute ha come parametri sia il file dello schema di mapping (SampleSchema.xml) che il file di dati XML (SampleXMLData.xml).</span><span class="sxs-lookup"><span data-stu-id="8d8cd-115">Notice also that the Execute method has as its parameters both the mapping schema file (SampleSchema.xml) and the XML data file (SampleXMLData.xml).</span></span> <span data-ttu-id="8d8cd-116">Quando si esegue il caricamento bulk, la tabella Cust creata nel database **tempdb** conterrà nuovi record basati sul contenuto del file di dati XML.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-116">When the bulk load executes, the Cust table you have created in **tempdb** database will contain new records based upon the contents of the XML data file.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="8d8cd-117">Per testare un caricamento bulk di esempio</span><span class="sxs-lookup"><span data-stu-id="8d8cd-117">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="8d8cd-118">Creare la tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-118">Create this table:</span></span>  
  
    ```  
    CREATE TABLE Cust(CustomerID  int PRIMARY KEY,  
                      CompanyName varchar(20),  
                      City        varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="8d8cd-119">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-119">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-120">Aggiungere lo schema XSD seguente al file:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-120">To this file, add the following XSD schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
       <xsd:element name="ROOT" sql:is-constant="1" >  
         <xsd:complexType>  
           <xsd:sequence>  
             <xsd:element name="Customers" sql:relation="Cust" maxOccurs="unbounded">  
               <xsd:complexType>  
                 <xsd:sequence>  
                   <xsd:element name="CustomerID"  type="xsd:integer" />  
                   <xsd:element name="CompanyName" type="xsd:string" />  
                   <xsd:element name="City"        type="xsd:string" />  
                 </xsd:sequence>  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
          </xsd:complexType>  
         </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="8d8cd-121">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-121">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="8d8cd-122">Aggiungere il documento XML seguente al file:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-122">To this file, add the following XML document:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Sean Chai</CompanyName>  
        <City>New York</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Tom Johnston</CompanyName>  
         <City>Los Angeles</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Institute of Art</CompanyName>  
        <City>Chicago</City>  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="8d8cd-123">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-123">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="8d8cd-124">Aggiungere al file il codice VBScript fornito all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-124">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="8d8cd-125">Modificare la stringa di connessione per specificare il nome del server appropriato.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-125">Modify the connection string to provide the appropriate server name.</span></span> <span data-ttu-id="8d8cd-126">Specificare il percorso appropriato per i file specificati come parametri del metodo Execute.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-126">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="8d8cd-127">Eseguire il codice VBScript.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-127">Execute the VBScript code.</span></span> <span data-ttu-id="8d8cd-128">Il caricamento bulk XML carica il file XML nella tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-128">XML Bulk Load loads the XML into the Cust table.</span></span>  
  
 <span data-ttu-id="8d8cd-129">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-129">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers"  sql:relation="Cust" >  
      <element type="CustomerID"  sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City"        sql:field="City" />  
  
   </ElementType>  
</Schema>  
```  
  
## <a name="b-bulk-loading-xml-data-in-multiple-tables"></a><span data-ttu-id="8d8cd-130">B.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-130">B.</span></span> <span data-ttu-id="8d8cd-131">Caricamento bulk di dati XML in più tabelle</span><span class="sxs-lookup"><span data-stu-id="8d8cd-131">Bulk loading XML data in multiple tables</span></span>  
 <span data-ttu-id="8d8cd-132">In questo esempio il documento XML è costituito dagli **\<Customer>** **\<Order>** elementi e.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-132">In this example, the XML document consists of the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Sean Chai</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Tom Johnston</CompanyName>  
     <City>LA</City>    
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Institute of Art</CompanyName>  
    <Order OrderID="4" />  
  </Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="8d8cd-133">Questo esempio esegue il caricamento bulk dei dati XML in due tabelle, **cust** e **CustOrder**:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-133">This example bulk loads the XML data into two tables, **Cust** and **CustOrder**:</span></span>  
  
```  
Cust(CustomerID, CompanyName, City)  
CustOrder(OrderID, CustomerID)  
```  
  
 <span data-ttu-id="8d8cd-134">Nello schema XSD seguente viene definita la vista XML delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-134">The following XSD schema defines the XML view of these tables.</span></span> <span data-ttu-id="8d8cd-135">Lo schema specifica la relazione padre-figlio tra gli **\<Customer>** **\<Order>** elementi e.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-135">The schema specifies the parent-child relationship between the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Customers" sql:relation="Cust" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="CustomerID"  type="xsd:integer" />  
              <xsd:element name="CompanyName" type="xsd:string" />  
              <xsd:element name="City"        type="xsd:string" />  
              <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
                <xsd:complexType>  
                  <xsd:attribute name="OrderID" type="xsd:integer" />  
                </xsd:complexType>  
              </xsd:element>  
             </xsd:sequence>  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="8d8cd-136">Il caricamento bulk XML utilizza la relazione di chiave primaria/chiave esterna specificata in precedenza tra gli **\<Cust>** **\<CustOrder>** elementi e per eseguire il caricamento bulk dei dati in entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-136">XML Bulk Load uses the primary key/foreign key relationship specified above between the **\<Cust>** and **\<CustOrder>** elements to bulk load the data into both tables.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="8d8cd-137">Per testare un caricamento bulk di esempio</span><span class="sxs-lookup"><span data-stu-id="8d8cd-137">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="8d8cd-138">Creare due tabelle nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="8d8cd-138">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
           CustomerID  int PRIMARY KEY,  
           CompanyName varchar(20),  
           City        varchar(20));  
    CREATE TABLE CustOrder(        OrderID     int PRIMARY KEY,   
            CustomerID int FOREIGN KEY REFERENCES Cust(CustomerID));  
    ```  
  
2.  <span data-ttu-id="8d8cd-139">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-139">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-140">Aggiungere lo schema XSD fornito in questo esempio al file.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-140">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="8d8cd-141">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-141">Create a file in your preferred text or XML editor, and save it as SampleData.xml.</span></span> <span data-ttu-id="8d8cd-142">Aggiungere al file il documento XML fornito in precedenza in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-142">Add the XML document that was provided earlier in this example to the file.</span></span>  
  
4.  <span data-ttu-id="8d8cd-143">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-143">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="8d8cd-144">Aggiungere al file il codice VBScript fornito all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-144">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="8d8cd-145">Modificare la stringa di connessione per specificare i nomi del server e del database appropriati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-145">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="8d8cd-146">Specificare il percorso appropriato per i file specificati come parametri del metodo Execute.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-146">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="8d8cd-147">Eseguire il codice VBScript indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-147">Execute the VBScript code above.</span></span> <span data-ttu-id="8d8cd-148">Il caricamento bulk XML carica il documento XML nelle tabelle Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-148">XML Bulk Load loads the XML document into the Cust and CustOrder tables.</span></span>  
  
 <span data-ttu-id="8d8cd-149">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-149">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
<sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="c-using-chain-relationships-in-the-schema-to-bulk-load-xml"></a><span data-ttu-id="8d8cd-150">C.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-150">C.</span></span> <span data-ttu-id="8d8cd-151">Utilizzo di relazioni a catena nello schema per il caricamento bulk XML</span><span class="sxs-lookup"><span data-stu-id="8d8cd-151">Using chain relationships in the schema to bulk load XML</span></span>  
 <span data-ttu-id="8d8cd-152">In questo esempio viene illustrata la modalità di utilizzo della relazione M:N specificata nello schema di mapping dal caricamento bulk XML per caricare dati in una tabella che rappresenta una relazione M:N.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-152">This example illustrates how the M:N relationship that is specified in the mapping schema is used by XML Bulk Load to load data in a table that represents an M:N relationship.</span></span>  
  
 <span data-ttu-id="8d8cd-153">Si consideri, ad esempio, lo schema XSD seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-153">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Ord"  
          parent-key="OrderID"  
          child="OrderDetail"  
          child-key="OrderID" />  
  
    <sql:relationship name="ODProduct"  
          parent="OrderDetail"  
          parent-key="ProductID"  
          child="Product"  
          child-key="ProductID"   
          inverse="true"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Ord"   
                     sql:key-fields="OrderID" >  
          <xsd:complexType>  
            <xsd:sequence>  
             <xsd:element name="Product"  
                          sql:relation="Product"   
                          sql:key-fields="ProductID"  
                          sql:relationship="OrderOD ODProduct">  
               <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
           <xsd:attribute name="OrderID"   type="xsd:integer" />   
           <xsd:attribute name="CustomerID"   type="xsd:string" />  
         </xsd:complexType>  
       </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="8d8cd-154">Lo schema specifica un **\<Order>** elemento con un **\<Product>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-154">The schema specifies an **\<Order>** element with a **\<Product>** child element.</span></span> <span data-ttu-id="8d8cd-155">L' **\<Order>** elemento esegue il mapping alla tabella Ord e l' **\<Product>** elemento viene mappato alla tabella Product nel database.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-155">The **\<Order>** element maps to Ord table and the **\<Product>** element maps to the Product table in the database.</span></span> <span data-ttu-id="8d8cd-156">La relazione di catena specificata nell' **\<Product>** elemento identifica una relazione M:N rappresentata dalla tabella OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-156">The chain relationship specified on the **\<Product>** element identifies a M:N relationship represented by the OrderDetail table.</span></span> <span data-ttu-id="8d8cd-157">Un ordine può includere molti prodotti e un prodotto può essere incluso in molti ordini.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-157">(An order can include many products, and a product can be included in many orders.)</span></span>  
  
 <span data-ttu-id="8d8cd-158">Quando si esegue il caricamento bulk di un documento XML con questo schema, vengono aggiunti record alle tabelle Ord, Product e OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-158">When you are bulk loading an XML document with this schema, records are added to the Ord, Product, and OrderDetail tables.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="8d8cd-159">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="8d8cd-159">To test a working sample</span></span>  
  
1.  <span data-ttu-id="8d8cd-160">Creare tre tabelle:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-160">Create three tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="8d8cd-161">Salvare lo schema fornito in precedenza in questo esempio come file SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-161">Save the schema that is provided above in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="8d8cd-162">Salvare i dati XML di esempio seguenti come file SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-162">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="1" CustomerID="ALFKI">  
        <Product ProductID="1" ProductName="Chai" />  
        <Product ProductID="2" ProductName="Chang" />  
      </Order>  
      <Order OrderID="2" CustomerID="ANATR">  
        <Product ProductID="3" ProductName="Aniseed Syrup" />  
        <Product ProductID="4" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="8d8cd-163">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-163">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="8d8cd-164">Aggiungere al file il codice VBScript fornito all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-164">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="8d8cd-165">Modificare la stringa di connessione per specificare i nomi del server e del database appropriati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-165">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="8d8cd-166">Rimuovere il commento dalle righe seguenti nel codice sorgente per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-166">Uncomment the following lines from the source code for this example.</span></span>  
  
    ```  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    ```  
  
5.  <span data-ttu-id="8d8cd-167">Eseguire il codice VBScript.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-167">Execute the VBScript code.</span></span> <span data-ttu-id="8d8cd-168">Il caricamento bulk XML carica il documento XML nelle tabelle Ord e Product.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-168">XML Bulk Load loads the XML document into the Ord and Product tables.</span></span>  
  
## <a name="d-bulk-loading-in-identity-type-columns"></a><span data-ttu-id="8d8cd-169">D.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-169">D.</span></span> <span data-ttu-id="8d8cd-170">Caricamento bulk in colonne di tipo Identity</span><span class="sxs-lookup"><span data-stu-id="8d8cd-170">Bulk loading in identity type columns</span></span>  
 <span data-ttu-id="8d8cd-171">In questo esempio viene illustrata la modalità di gestione delle colonne di tipo Identity da parte del caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-171">This example illustrates how bulk load handles identity type columns.</span></span> <span data-ttu-id="8d8cd-172">Nell'esempio viene eseguito il caricamento bulk dei dati in tre tabelle, Ord, Product e OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-172">In the example, data is bulk loaded into three tables (Ord, Product, and OrderDetail).</span></span>  
  
 <span data-ttu-id="8d8cd-173">In tali tabelle:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-173">In these tables:</span></span>  
  
-   <span data-ttu-id="8d8cd-174">OrderID nella tabella Ord è una colonna di tipo Identity.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-174">OrderID in the Ord table is an identity type column</span></span>  
  
-   <span data-ttu-id="8d8cd-175">ProductID nella tabella Product è una colonna di tipo Identity.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-175">ProductID in the Product table is an identity type column.</span></span>  
  
-   <span data-ttu-id="8d8cd-176">Le colonne OrderID e ProductID in OrderDetail sono colonne chiavi esterne che fanno riferimento alle colonne chiavi primarie corrispondenti nelle tabelle Ord e Product.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-176">OrderID and ProductID columns in the OrderDetail are foreign key columns referring to corresponding primary key columns in the Ord and Product tables.</span></span>  
  
 <span data-ttu-id="8d8cd-177">Di seguito vengono indicati gli schemi di tabella per l'esempio:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-177">The following are the table schemas for this example:</span></span>  
  
```  
Ord (OrderID, CustomerID)  
Product (ProductID, ProductName)  
OrderDetail (OrderID, ProductID)  
```  
  
 <span data-ttu-id="8d8cd-178">In questo esempio di caricamento bulk XML, la proprietà KeepIdentity del modello a oggetti BulkLoad è impostata su false.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-178">In this example of XML Bulk Load, the KeepIdentity property of the BulkLoad object model is set to false.</span></span> <span data-ttu-id="8d8cd-179">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] genera pertanto valori Identity per le colonne ProductID e OrderID rispettivamente nelle tabelle Product e Ord. Qualsiasi valore fornito nei documenti di cui eseguire un caricamento bulk viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-179">Therefore, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] generates identity values for the ProductID and OrderID columns in the Product and Ord tables, respectively (any values provided in the documents to be bulk loaded are ignored).</span></span>  
  
 <span data-ttu-id="8d8cd-180">In questo caso, il caricamento bulk XML identifica la relazione di chiave primaria/chiave esterna nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-180">In this case, XML Bulk Load identifies the primary key/foreign key relationship among tables.</span></span> <span data-ttu-id="8d8cd-181">Il caricamento bulk inserisce innanzitutto record nelle tabelle con la chiave primaria, quindi propaga il valore Identity generato in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nelle tabelle con le colonne chiavi esterne.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-181">Bulk Load first inserts records in the tables with the primary key, then propagates the identity value generated by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the tables with foreign key columns.</span></span> <span data-ttu-id="8d8cd-182">Nell'esempio seguente il caricamento bulk XML inserisce dati nelle tabelle in base all'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-182">In the following example, XML Bulk Load inserts data in tables in this order:</span></span>  
  
1.  <span data-ttu-id="8d8cd-183">Prodotto</span><span class="sxs-lookup"><span data-stu-id="8d8cd-183">Product</span></span>  
  
2.  <span data-ttu-id="8d8cd-184">Ord</span><span class="sxs-lookup"><span data-stu-id="8d8cd-184">Ord</span></span>  
  
3.  <span data-ttu-id="8d8cd-185">OrderDetail</span><span class="sxs-lookup"><span data-stu-id="8d8cd-185">OrderDetail</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d8cd-186">Per propagare i valori Identity generati nelle tabelle Products e Orders, la logica di elaborazione richiede che il caricamento bulk XML tenga traccia di tali valori per l'inserimento successivo nella tabella OrderDetails.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-186">In order to propagate identity values generated in the Products and Orders tables, the processing logic requires XML Bulk Load to keep track of these values for later insertion into the OrderDetails table.</span></span> <span data-ttu-id="8d8cd-187">A tale scopo, il caricamento bulk XML crea tabelle intermedie, popola i dati in tali tabelle e successivamente li rimuove.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-187">To do that, XML Bulk Load creates intermediate tables, populates the data in these tables, and later removes them.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="8d8cd-188">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="8d8cd-188">To test a working sample</span></span>  
  
1.  <span data-ttu-id="8d8cd-189">Creare le tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-189">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="8d8cd-190">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-190">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-191">Aggiungere lo schema XSD seguente al file.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-191">Add this XSD schema to this file.</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
       <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
       </xsd:appinfo>  
     </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="8d8cd-192">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-192">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="8d8cd-193">Aggiungere il documento XML seguente.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-193">Add the following XML document.</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="8d8cd-194">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-194">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="8d8cd-195">Aggiungere al file il codice VBScript seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-195">To this file, add the following VBScript code.</span></span> <span data-ttu-id="8d8cd-196">Modificare la stringa di connessione per specificare i nomi del server e del database appropriati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-196">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="8d8cd-197">Specificare il percorso appropriato per i file che vengono usati come parametri per il `Execute` metodo.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-197">Specify the appropriate path for the files that serve as parameters to the `Execute` method.</span></span>  
  
    ```  
    Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "C:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction = False  
    objBL.KeepIdentity = False  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    Set objBL = Nothing  
    MsgBox "Done."  
    ```  
  
5.  <span data-ttu-id="8d8cd-198">Eseguire il codice VBScript.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-198">Execute the VBScript code.</span></span> <span data-ttu-id="8d8cd-199">Il caricamento bulk XML caricherà i dati nelle tabelle appropriate.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-199">The XML Bulk Load will load the data into the appropriate tables.</span></span>  
  
## <a name="e-generating-table-schemas-before-bulk-loading"></a><span data-ttu-id="8d8cd-200">E.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-200">E.</span></span> <span data-ttu-id="8d8cd-201">Generazione di schemi di tabella prima del caricamento bulk</span><span class="sxs-lookup"><span data-stu-id="8d8cd-201">Generating table schemas before bulk loading</span></span>  
 <span data-ttu-id="8d8cd-202">Il caricamento bulk XML può eventualmente generare le tabelle se queste non sono già presenti.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-202">XML Bulk Load can optionally generate the tables if they do not exist before bulk loading.</span></span> <span data-ttu-id="8d8cd-203">Questa operazione viene eseguita impostando la proprietà SchemaGen dell'oggetto SQLXMLBulkLoad su TRUE.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-203">Setting the SchemaGen property of the SQLXMLBulkLoad object to TRUE does this.</span></span> <span data-ttu-id="8d8cd-204">Facoltativamente, è anche possibile richiedere il caricamento bulk XML per eliminare tutte le tabelle esistenti e ricrearle impostando la proprietà SGDropTables su TRUE.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-204">You can also optionally request XML Bulk Load to drop any existing tables and re-create them by setting the SGDropTables property to TRUE.</span></span> <span data-ttu-id="8d8cd-205">Nell'esempio di codice VBScript seguente viene illustrato l'utilizzo di tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-205">The following VBScript example illustrates the use of these properties.</span></span>  
  
 <span data-ttu-id="8d8cd-206">Nell'esempio vengono inoltre impostate altre due proprietà su TRUE:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-206">Also, this example sets two additional properties to TRUE:</span></span>  
  
-   <span data-ttu-id="8d8cd-207">CHECKCONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-207">CheckConstraints.</span></span> <span data-ttu-id="8d8cd-208">Impostando questa proprietà su TRUE, è possibile garantire che i dati inseriti nelle tabelle non violino eventuali vincoli specificati nelle tabelle, in questo caso i vincoli PRIMARY KEY/FOREIGN KEY specificati tra le tabelle Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-208">Setting this property to TRUE ensures that the data being inserted into the tables does not violate any constraints that have been specified on the tables (in this case the PRIMARY KEY/FOREIGN KEY constraints specified between the Cust and CustOrder tables).</span></span> <span data-ttu-id="8d8cd-209">In caso di violazione di vincoli, il caricamento bulk non riesce.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-209">If there is a constraint violation, the bulk load fails.</span></span>  
  
-   <span data-ttu-id="8d8cd-210">XmlFragment.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-210">XMLFragment.</span></span> <span data-ttu-id="8d8cd-211">Questa proprietà deve essere impostata su TRUE perché il documento XML di esempio (origine dati) non contiene singoli elementi di livello principale ed è pertanto un frammento.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-211">This property must be set to TRUE because the sample XML document (data source) contains no single, top-level element (and is thus a fragment).</span></span>  
  
 <span data-ttu-id="8d8cd-212">Di seguito viene fornito il codice VBScript:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-212">This is the VBScript code:</span></span>  
  
```  
Dim objBL   
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
objBL.CheckConstraints=true  
objBL.XMLFragment = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="8d8cd-213">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="8d8cd-213">To test a working sample</span></span>  
  
1.  <span data-ttu-id="8d8cd-214">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-214">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-215">Aggiungere al file lo schema XSD fornito nell'esempio precedente "Utilizzo di relazioni a catena nello schema per il caricamento bulk XML".</span><span class="sxs-lookup"><span data-stu-id="8d8cd-215">Add the XSD schema that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span>  
  
2.  <span data-ttu-id="8d8cd-216">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-216">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="8d8cd-217">Aggiungere al file il documento XML fornito nell'esempio precedente "Utilizzo di relazioni a catena nello schema per il caricamento bulk XML".</span><span class="sxs-lookup"><span data-stu-id="8d8cd-217">Add the XML document that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span> <span data-ttu-id="8d8cd-218">Rimuovere l' \<ROOT> elemento dal documento (per impostarlo come frammento).</span><span class="sxs-lookup"><span data-stu-id="8d8cd-218">Remove the \<ROOT> element from the document (to make it a fragment).</span></span>  
  
3.  <span data-ttu-id="8d8cd-219">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-219">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="8d8cd-220">Aggiungere al file il codice VBScript fornito in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-220">To this file, add the VBScript code in this example.</span></span> <span data-ttu-id="8d8cd-221">Modificare la stringa di connessione per specificare i nomi del server e del database appropriati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-221">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="8d8cd-222">Specificare il percorso appropriato per i file specificati come parametri del metodo Execute.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-222">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
4.  <span data-ttu-id="8d8cd-223">Eseguire il codice VBScript.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-223">Execute the VBScript code.</span></span> <span data-ttu-id="8d8cd-224">Il caricamento bulk XML crea le tabelle necessarie in base allo schema di mapping fornito e vi esegue il caricamento bulk dei dati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-224">The XML Bulk Load creates the necessary tables on the basis of the mapping schema that is provided and bulk loads the data in it.</span></span>  
  
## <a name="f-bulk-loading-from-a-stream"></a><span data-ttu-id="8d8cd-225">F.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-225">F.</span></span> <span data-ttu-id="8d8cd-226">Caricamento bulk da un flusso</span><span class="sxs-lookup"><span data-stu-id="8d8cd-226">Bulk loading from a stream</span></span>  
 <span data-ttu-id="8d8cd-227">Il metodo Execute del modello a oggetti per il caricamento bulk XML accetta due parametri.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-227">The Execute method of the XML Bulk Load object model takes two parameters.</span></span> <span data-ttu-id="8d8cd-228">Il primo parametro corrisponde al file dello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-228">The first parameter is the mapping schema file.</span></span> <span data-ttu-id="8d8cd-229">Il secondo parametro fornisce i dati XML da caricare nel database.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-229">The second parameter provides the XML data that is to be loaded in the database.</span></span> <span data-ttu-id="8d8cd-230">Esistono due modi per passare i dati XML al metodo Execute del caricamento bulk XML:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-230">There are two ways to pass the XML data to the Execute method of XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="8d8cd-231">Specificare il nome di file come parametro.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-231">Specify the file name as the parameter.</span></span>  
  
-   <span data-ttu-id="8d8cd-232">Passare un flusso contenente i dati XML.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-232">Pass a stream that contains the XML data.</span></span>  
  
 <span data-ttu-id="8d8cd-233">In questo esempio viene illustrato come eseguire un caricamento bulk da un flusso.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-233">This example illustrates how to bulk load from a stream.</span></span>  
  
 <span data-ttu-id="8d8cd-234">VBScript esegue innanzitutto un'istruzione SELECT per recuperare informazioni sui clienti dalla tabella Customers del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-234">VBScript first executes a SELECT statement to retrieve customer information from the Customers table in the Northwind database.</span></span> <span data-ttu-id="8d8cd-235">Poiché nell'istruzione SELECT è specificata la clausola FOR XML (con l'opzione ELEMENTS), la query restituisce un documento XML incentrato sugli elementi nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-235">Because the FOR XML clause is specified (with the ELEMENTS option) in the SELECT statement, the query returns an element-centric XML document of this form:</span></span>  
  
```  
<Customer>  
  <CustomerID>..</CustomerID>  
  <CompanyName>..</CompanyName>  
  <City>..</City>  
</Customer>  
...  
```  
  
 <span data-ttu-id="8d8cd-236">Lo script passa quindi il codice XML come flusso al metodo Execute come secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-236">The script then passes the XML as a stream to the Execute method as its second parameter.</span></span> <span data-ttu-id="8d8cd-237">Il metodo Execute esegue il caricamento bulk dei dati nella tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-237">The Execute method bulk loads the data into the Cust table.</span></span>  
  
 <span data-ttu-id="8d8cd-238">Poiché questo script imposta la proprietà SchemaGen su TRUE e la proprietà SGDropTables su TRUE, il caricamento bulk XML crea la tabella Cust nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-238">Because this script sets the SchemaGen property to TRUE and SGDropTables property to TRUE, XML Bulk Load creates the Cust table in the specified database.</span></span> <span data-ttu-id="8d8cd-239">Se la tabella è già presente, questa viene innanzitutto eliminata e quindi ricreata.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-239">(If the table already exists, it first drops the table and then re-creates it.)</span></span>  
  
 <span data-ttu-id="8d8cd-240">Di seguito viene fornito l'esempio di codice di VBScript.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-240">This is the VBScript example:</span></span>  
  
```  
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
Set objCmd = CreateObject("ADODB.Command")  
Set objConn = CreateObject("ADODB.Connection")  
Set objStrmOut = CreateObject ("ADODB.Stream")  
  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile     = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen        = True  
objBL.SGDropTables     = True  
objBL.XMLFragment      = True  
' Open a connection to the instance of SQL Server to get the source data.  
  
objConn.Open "provider=SQLOLEDB;server=(local);database=tempdb;integrated security=SSPI"  
Set objCmd.ActiveConnection = objConn  
objCmd.CommandText = "SELECT CustomerID, CompanyName, City FROM Customers FOR XML AUTO, ELEMENTS"  
  
' Open the return stream and execute the command.  
Const adCRLF = -1  
Const adExecuteStream = 1024  
objStrmOut.Open  
objStrmOut.LineSeparator = adCRLF  
objCmd.Properties("Output Stream").Value = objStrmOut  
objCmd.Execute , , adExecuteStream  
objStrmOut.Position = 0  
  
' Execute bulk load. Read source XML data from the stream.  
objBL.Execute "SampleSchema.xml", objStrmOut  
  
Set objBL = Nothing  
```  
  
 <span data-ttu-id="8d8cd-241">Nello schema di mapping XSD seguente vengono fornite le informazioni necessarie per creare la tabella:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-241">The following XSD mapping schema provides the necessary information to create the table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="true" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customers"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="Customers" sql:relation="Cust" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element name="CustomerID"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(5)"/>  
      <xsd:element name="CompanyName"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
      <xsd:element name="City"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="8d8cd-242">Di seguito viene fornito lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-242">This is equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
    </ElementType>  
</Schema>  
```  
  
### <a name="opening-a-stream-on-an-existing-file"></a><span data-ttu-id="8d8cd-243">Apertura di un flusso in un file esistente</span><span class="sxs-lookup"><span data-stu-id="8d8cd-243">Opening a Stream on an Existing File</span></span>  
 <span data-ttu-id="8d8cd-244">È anche possibile aprire un flusso in un file di dati XML esistente e passare il flusso come parametro al metodo Execute, anziché passare il nome del file come parametro.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-244">You can also open a stream on an existing XML data file and pass the stream as a parameter to the Execute method (instead of passing the file name as the parameter).</span></span>  
  
 <span data-ttu-id="8d8cd-245">Di seguito viene fornito un esempio di passaggio di un flusso come parametro in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-245">This is a Visual Basic example of passing a stream as the parameter:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad  
Dim objStrm As New ADODB.Stream  
Dim objFileSystem As New Scripting.FileSystemObject  
Dim objFile As Scripting.TextStream  
  
MsgBox "Begin BulkLoad..."  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
' Here again a stream is specified that contains the source data   
' (instead of the file name). But this is just an illustration.  
' Usually this is useful if you have an XML data   
' stream that is created by some other means that you want to bulk   
' load. This example starts with an XML text file, so it may not be the   
' best to use a stream (you can specify the file name directly).  
' Here you could have specified the file name itself.   
Set objFile = objFileSystem.OpenTextFile("c:\SampleData.xml")  
objStrm.Open  
objStrm.WriteText objFile.ReadAll  
objStrm.Position = 0  
objBL.Execute "c:\SampleSchema.xml", objStrm  
  
Set objBL = Nothing  
MsgBox "Done."  
End Sub  
```  
  
 <span data-ttu-id="8d8cd-246">Per testare l'applicazione, utilizzare il documento XML seguente in un file (SampleData.xml) e lo schema XSD fornito in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-246">To test the application, use the following XML document in a file (SampleData.xml) and the XSD schema that is provided in this example:</span></span>  
  
 <span data-ttu-id="8d8cd-247">Di seguito viene fornita l'origine dati XML (SampleData.xml):</span><span class="sxs-lookup"><span data-stu-id="8d8cd-247">This is the XML source data (SampleData.xml):</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Hanari Carnes</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Toms Spezialitten</CompanyName>  
     <City>LA</City>  
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Victuailles en stock</CompanyName>  
    <Order CustomerID= "4444" OrderID="4" />  
</Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="8d8cd-248">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-248">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="g-bulk-loading-in-overflow-columns"></a><span data-ttu-id="8d8cd-249">G.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-249">G.</span></span> <span data-ttu-id="8d8cd-250">Caricamento bulk in colonne di overflow</span><span class="sxs-lookup"><span data-stu-id="8d8cd-250">Bulk loading in overflow columns</span></span>  
 <span data-ttu-id="8d8cd-251">Se lo schema di mapping specifica una colonna di overflow tramite l'annotazione `sql:overflow-field`, il caricamento bulk XML copia tutti i dati non utilizzati dal documento di origine in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-251">If the mapping schema specifies an overflow column by using the `sql:overflow-field` annotation, XML Bulk Load copies all unconsumed data from the source document into this column.</span></span>  
  
 <span data-ttu-id="8d8cd-252">Si consideri lo schema XSD seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-252">Consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
          <xsd:attribute name="CustomerID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="8d8cd-253">Lo schema identifica una colonna di overflow (OverflowColumn) per la tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-253">The schema identifies an overflow column (OverflowColumn) for the Cust table.</span></span> <span data-ttu-id="8d8cd-254">Di conseguenza, tutti i dati XML non utilizzati per ogni **\<Customer>** elemento vengono aggiunti a questa colonna.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-254">As a result, all unconsumed XML data for each **\<Customer>** element is added to this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d8cd-255">Tutti gli elementi astratti (elementi per cui è specificato **abstract = "true"** ) e tutti gli attributi non consentiti (gli attributi per i quali non è **consentito = "true"** ) vengono considerati overflow dal caricamento bulk XML e vengono aggiunti alla colonna di overflow, se specificato.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-255">All abstract elements (elements for which **abstract="true"** is specified) and all prohibited attributes (attributes for which **prohibited="true"** is specified) are considered overflow by XML Bulk Load and are added to the overflow column, if specified.</span></span> <span data-ttu-id="8d8cd-256">In caso contrario, vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-256">(Otherwise, they are ignored.)</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="8d8cd-257">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="8d8cd-257">To test a working sample</span></span>  
  
1.  <span data-ttu-id="8d8cd-258">Creare due tabelle nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="8d8cd-258">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle',  
                  OverflowColumn nvarchar(200));  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID    int PRIMARY KEY,  
                  CustomerID int FOREIGN KEY   
                                 REFERENCES Cust(CustomerID));  
    GO  
    ```  
  
2.  <span data-ttu-id="8d8cd-259">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-259">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-260">Aggiungere lo schema XSD fornito in questo esempio al file.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-260">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="8d8cd-261">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-261">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="8d8cd-262">Aggiungere il seguente documento XML al file:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-262">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City><![CDATA[NY]]> </City>  
        <Junk>garbage in overflow</Junk>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <![CDATA[LA]]>   
        <!-- <xyz><address>111 Maple, Seattle</address></xyz>   -->  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="8d8cd-263">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-263">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="8d8cd-264">Aggiungere a questo file il codice Microsoft Visual Basic, Scripting Edition (VBScript) seguente.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-264">To this file, add the following Microsoft Visual Basic Scripting Edition (VBScript) code.</span></span> <span data-ttu-id="8d8cd-265">Modificare la stringa di connessione per specificare i nomi del server e del database appropriati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-265">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="8d8cd-266">Specificare il percorso appropriato per i file specificati come parametri del metodo Execute.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-266">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="8d8cd-267">Eseguire il codice VBScript.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-267">Execute the VBScript code.</span></span>  
  
 <span data-ttu-id="8d8cd-268">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-268">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"   
                       sql:overflow-field="OverflowColumn"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="h-specifying-the-file-path-for-temp-files-in-transaction-mode"></a><span data-ttu-id="8d8cd-269">H.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-269">H.</span></span> <span data-ttu-id="8d8cd-270">Impostazione del percorso dei file temporanei in modalità transazione</span><span class="sxs-lookup"><span data-stu-id="8d8cd-270">Specifying the file path for temp files in transaction mode</span></span>  
 <span data-ttu-id="8d8cd-271">Quando si esegue il caricamento bulk in modalità transazione, ovvero quando la proprietà Transaction è impostata su TRUE, è necessario impostare anche la proprietà TempFilePath quando si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-271">When you are bulk loading in transaction mode (that is, when the Transaction property is set to TRUE), you also must set the TempFilePath property when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="8d8cd-272">Viene eseguito un caricamento bulk in un server remoto.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-272">You are bulk loading to a remote server.</span></span>  
  
-   <span data-ttu-id="8d8cd-273">Si desidera utilizzare un'unità locale o una cartella alternativa, diversa dal percorso specificato dalla variabile di ambiente TEMP, per archiviare i file temporanei creati in modalità transazione.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-273">You want to use an alternate local drive or folder (one other than the path that is specified by the TEMP environment variable) to store the temporary files that are created in the transaction mode.</span></span>  
  
 <span data-ttu-id="8d8cd-274">Il codice VBScript seguente, ad esempio, esegue il caricamento bulk dei dati dal file SampleXMLData.xml nelle tabelle di database in modalità transazione.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-274">For example, the following VBScript code bulk loads data from the SampleXMLData.xml file into the database tables in transaction mode.</span></span> <span data-ttu-id="8d8cd-275">Per impostare il percorso dei file temporanei generati in modalità transazione, viene specificata la proprietà TempFilePath.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-275">The TempFilePath property is specified to set the path for the temporary files that are generated in transaction mode.</span></span>  
  
```  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.Transaction=True  
objBL.TempFilePath="\\Server\MyDir"  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
set objBL=Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="8d8cd-276">Il percorso dei file temporanei deve essere un percorso condiviso a cui l'account del servizio dell'istanza di destinazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e l'account che esegue l'applicazione di caricamento bulk possano accedere.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-276">The temporary file path must be a shared location that is accessible to the service account of the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and to the account that is running the bulk load application.</span></span> <span data-ttu-id="8d8cd-277">A meno che non si stia caricando il caricamento bulk in un server locale, il percorso del file temporaneo deve essere un percorso UNC, ad esempio \\ \nomeserver\nomecondivisione.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-277">Unless you are bulk loading on a local server, the temporary file path must be a UNC path (such as \\\servername\sharename).</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="8d8cd-278">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="8d8cd-278">To test a working sample</span></span>  
  
1.  <span data-ttu-id="8d8cd-279">Creare questa tabella nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="8d8cd-279">Create this table in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (     CustomerID uniqueidentifier,   
          LastName  varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="8d8cd-280">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-280">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-281">Aggiungere lo schema XSD seguente al file:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-281">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="8d8cd-282">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-282">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="8d8cd-283">Aggiungere il seguente documento XML al file:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-283">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="6F9619FF-8B86-D011-B42D-00C04FC964FF"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="8d8cd-284">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-284">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="8d8cd-285">Aggiungere al file il codice VBScript seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-285">To this file, add the following VBScript code.</span></span> <span data-ttu-id="8d8cd-286">Modificare la stringa di connessione per specificare i nomi del server e del database appropriati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-286">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="8d8cd-287">Specificare il percorso appropriato per i file specificati come parametri del metodo Execute.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-287">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span> <span data-ttu-id="8d8cd-288">Specificare anche il percorso appropriato per la proprietà TempFilePath.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-288">Also specify the appropriate path for the TempFilePath property.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.TempFilePath="\\server\folder"  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="8d8cd-289">Eseguire il codice VBScript.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-289">Execute the VBScript code.</span></span>  
  
     <span data-ttu-id="8d8cd-290">`sql:datatype`Quando il valore di **CustomerID** viene specificato come GUID che include parentesi graffe ({e}), lo schema deve specificare l'oggetto corrispondente per l'attributo **CustomerID** , ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-290">The schema must specify the corresponding `sql:datatype` for the **CustomerID** attribute when the value for **CustomerID** is specified as a GUID that includes braces ({ and }), such as:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="{6F9619FF-8B86-D011-B42D-00C04FC964FF}"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
     <span data-ttu-id="8d8cd-291">Di seguito viene fornito lo schema aggiornato:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-291">This is the updated schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string"   
                        sql:datatype="uniqueidentifier" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
     <span data-ttu-id="8d8cd-292">Quando `sql:datatype` si specifica l'identificazione del tipo di colonna come `uniqueidentifier` , l'operazione di caricamento bulk rimuove le parentesi graffe ({e}) dal valore **CustomerID** prima di inserirlo nella colonna.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-292">When `sql:datatype` is specified identifying the column type as `uniqueidentifier`, the bulk load operation removes the braces ({ and }) from the **CustomerID** value before inserting it in the column.</span></span>  
  
 <span data-ttu-id="8d8cd-293">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-293">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
<ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
</ElementType>  
<ElementType name="Customers" sql:relation="Cust" >  
  <AttributeType name="CustomerID"  sql:datatype="uniqueidentifier" />  
  <AttributeType name="LastName"   />  
  
  <attribute type="CustomerID" />  
  <attribute type="LastName"   />  
</ElementType>  
</Schema>  
```  
  
## <a name="i-using-an-existing-database-connection-with-the-connectioncommand-property"></a><span data-ttu-id="8d8cd-294">I.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-294">I.</span></span> <span data-ttu-id="8d8cd-295">Utilizzo di una connessione al database esistente con la proprietà ConnectionCommand</span><span class="sxs-lookup"><span data-stu-id="8d8cd-295">Using an existing database connection with the ConnectionCommand property</span></span>  
 <span data-ttu-id="8d8cd-296">È possibile utilizzare una connessione ADO esistente per eseguire il caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-296">You can use an existing ADO connection to bulk load XML.</span></span> <span data-ttu-id="8d8cd-297">Si tratta di una scelta utile se il caricamento bulk XML è solo una delle numerose operazioni che verranno eseguite su un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-297">This is useful if XML Bulk Load is just one of many operations that will be performed on a data source.</span></span>  
  
 <span data-ttu-id="8d8cd-298">La proprietà ConnectionCommand consente di utilizzare una connessione ADO esistente utilizzando un oggetto comando ADO.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-298">The ConnectionCommand property enables you to use an existing ADO connection by using an ADO command object.</span></span> <span data-ttu-id="8d8cd-299">Questo comportamento viene illustrato nell'esempio di Visual Basic seguente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-299">This is illustrated in the following Visual Basic example:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad4  
Dim objCmd As New ADODB.Command  
Dim objConn As New ADODB.Connection  
  
'Open a connection to an instance of SQL Server.  
objConn.Open "provider=SQLOLEDB;data source=(local);database=tempdb;integrated security=SSPI"  
'Ask the Command object to use the connection just established.  
Set objCmd.ActiveConnection = objConn  
  
'Tell Bulk Load to use the active command object that is using the Connection obj.  
objBL.ConnectionCommand = objCmd  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
'The Transaction property must be set to True if you use ConnectionCommand.  
objBL.Transaction = True  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
End Sub  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="8d8cd-300">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="8d8cd-300">To test a working sample</span></span>  
  
1.  <span data-ttu-id="8d8cd-301">Creare due tabelle nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="8d8cd-301">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
                   CustomerID   varchar(5) PRIMARY KEY,  
                   CompanyName  varchar(30),  
                   City         varchar(20));  
    GO  
    CREATE TABLE CustOrder(  
                   CustomerID  varchar(5) references Cust (CustomerID),  
                   OrderID     varchar(5) PRIMARY KEY);  
    GO  
    ```  
  
2.  <span data-ttu-id="8d8cd-302">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-302">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-303">Aggiungere lo schema XSD seguente al file:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-303">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="CustCustOrder"  
              parent="Cust"  
              parent-key="CustomerID"  
              child="CustOrder"  
              child-key="CustomerID" />  
      </xsd:appinfo>  
    </xsd:annotation>  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:sequence>  
           <xsd:element name="CustomerID"  type="xsd:integer" />  
           <xsd:element name="CompanyName" type="xsd:string" />  
           <xsd:element name="City"        type="xsd:string" />  
           <xsd:element name="Order"   
                              sql:relation="CustOrder"  
                              sql:relationship="CustCustOrder" >  
             <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:integer" />  
             </xsd:complexType>  
           </xsd:element>  
         </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="8d8cd-304">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-304">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="8d8cd-305">Aggiungere il seguente documento XML al file:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-305">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="8d8cd-306">Creare un'applicazione Visual Basic (Standard EXE) e il codice precedente.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-306">Create a Visual Basic (Standard EXE) application and the preceding code.</span></span> <span data-ttu-id="8d8cd-307">Aggiungere i riferimenti seguenti al progetto:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-307">Add these references to the project:</span></span>  
  
    ```  
    Microsoft XML BulkLoad for SQL Server 4.0 Type Library  
    Microsoft ActiveX Data objects 2.6 Library  
    ```  
  
5.  <span data-ttu-id="8d8cd-308">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-308">Execute the application.</span></span>  
  
 <span data-ttu-id="8d8cd-309">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-309">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
         <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="j-bulk-loading-in-xml-data-type-columns"></a><span data-ttu-id="8d8cd-310">J.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-310">J.</span></span> <span data-ttu-id="8d8cd-311">Caricamento bulk in colonne con tipo di dati xml</span><span class="sxs-lookup"><span data-stu-id="8d8cd-311">Bulk loading in xml Data Type columns</span></span>  
 <span data-ttu-id="8d8cd-312">Se lo schema di mapping specifica una colonna con [tipo di dati XML](/sql/t-sql/xml/xml-transact-sql) tramite l' `sql:datatype="xml"` annotazione, il caricamento bulk XML è in grado di copiare elementi figlio XML per il campo mappato dal documento di origine in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-312">If the mapping schema specifies a [xml data type](/sql/t-sql/xml/xml-transact-sql) column by using the `sql:datatype="xml"` annotation, XML Bulk Load can copy XML child elements for the mapped field from the source document into this column.</span></span>  
  
 <span data-ttu-id="8d8cd-313">Si consideri lo schema XSD seguente, che esegue il mapping di una vista della tabella Production.ProductModel nel database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-313">Consider the following XSD schema, which maps a view of the Production.ProductModel table in the AdventureWorks sample database.</span></span> <span data-ttu-id="8d8cd-314">In questa tabella viene eseguito il mapping del campo CatalogDescription del `xml` tipo di dati a un **\<Desc>** elemento utilizzando le `sql:field` `sql:datatype="xml"` annotazioni e.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-314">In this table, the CatalogDescription field of `xml` data type is mapped to a **\<Desc>** element using the `sql:field` and `sql:datatype="xml"` annotations.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Name" type="xs:string"></xsd:element>  
        <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element name="ProductDescription">  
              <xsd:complexType>  
                <xsd:sequence>  
                  <xsd:element name="Summary" type="xs:anyType"/>  
                </xsd:sequence>  
              </xsd:complexType>  
            </xsd:element>  
          </xsd:sequence>  
        </xsd:complexType>  
        </xsd:element>   
     </xsd:sequence>  
     <xsd:attribute name="ProductModelID" sql:field="ProductModelID" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="8d8cd-315">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="8d8cd-315">To test a working sample</span></span>  
  
1.  <span data-ttu-id="8d8cd-316">Verificare che il database di esempio AdventureWorks sia installato.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-316">Verify that the AdventureWorks sample database is installed.</span></span>  
  
2.  <span data-ttu-id="8d8cd-317">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-317">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="8d8cd-318">Copiare lo schema XSD precedente, incollarlo nel file e salvarlo.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-318">Copy the XSD schema above and paste it into the file and save it.</span></span>  
  
3.  <span data-ttu-id="8d8cd-319">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-319">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="8d8cd-320">Copiare il documento XML seguente, incollarlo nel file e salvarlo nella stessa cartella utilizzata per il passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-320">Copy the following XML document below and paste it into the file and save it in the same folder as was used for the previous step.</span></span>  
  
    ```  
    <ProductModel ProductModelID="2005">  
        <Name>Mountain-100 (2005 model)</Name>  
        <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
            <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
                  xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
                  xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
                  xmlns:html="http://www.w3.org/1999/xhtml"   
                  xmlns="">  
                <p1:Summary>  
                    <html:p>Our top-of-the-line competition mountain bike.   
          Performance-enhancing options include the innovative HL Frame,   
          super-smooth front suspension, and traction for all terrain.  
                            </html:p>  
                </p1:Summary>  
                <p1:Manufacturer>  
                    <p1:Name>AdventureWorks</p1:Name>  
                    <p1:Copyright>2002-2005</p1:Copyright>  
                    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
                </p1:Manufacturer>  
                <p1:Features>These are the product highlights.   
                     <wm:Warranty>  
                        <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
                        <wm:Description>parts and labor</wm:Description>  
                    </wm:Warranty><wm:Maintenance>  
                        <wm:NoOfYears>10 years</wm:NoOfYears>  
                        <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
                    </wm:Maintenance><wf:wheel>High performance wheels.</wf:wheel><wf:saddle>  
                        <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle><wf:pedal>  
                        <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal><wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter   
          and wall-thickness required of a premium mountain frame.   
          The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame><wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset></p1:Features>  
                <!-- add one or more of these elements... one for each specific product in this product model -->  
                <p1:Picture>  
                    <p1:Angle>front</p1:Angle>  
                    <p1:Size>small</p1:Size>  
                    <p1:ProductPhotoID>118</p1:ProductPhotoID>  
                </p1:Picture>  
                <!-- add any tags in <specifications> -->  
                <p1:Specifications> These are the product specifications.  
                       <Material>Almuminum Alloy</Material><Color>Available in most colors</Color><ProductLine>Mountain bike</ProductLine><Style>Unisex</Style><RiderExperience>Advanced to Professional riders</RiderExperience></p1:Specifications>  
            </p1:ProductDescription>  
        </Desc>  
    </ProductModel>  
    ```  
  
4.  <span data-ttu-id="8d8cd-321">Creare un file nell'editor di testo o XML preferito e salvarlo con il nome BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-321">Create a file in your preferred text or XML editor, and save it as BulkloadXml.vbs.</span></span> <span data-ttu-id="8d8cd-322">Copiare il codice VBScript seguente e incollarlo nel file.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-322">Copy the following VBScript code and paste it into the file.</span></span> <span data-ttu-id="8d8cd-323">Salvarlo nella stessa cartella utilizzata per i dati e i file di XML Schema precedenti.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-323">Save it in the same folder as was used for the previous XML data and schema files.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=AdventureWorks;integrated security=SSPI"  
  
    Dim fso, sAppPath  
    Set fso = CreateObject("Scripting.FileSystemObject")   
    sAppPath = fso.GetFolder(".")   
  
    objBL.ErrorLogFile = sAppPath & "\error.log"  
  
    'Execute XML bulkload using file.  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="8d8cd-324">Eseguire lo script BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="8d8cd-324">Execute the BulkloadXml.vbs script.</span></span>  
  
  
