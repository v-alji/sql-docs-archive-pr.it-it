---
title: 'Filtro di valori tramite SQL: limit-field e SQL: Limit-Value (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, filtering values
- limiting values [SQLXML]
- limit-value annotation
- limit-field annotation
- sql:limit-field
- sql:limit-value
- filtering [SQLXML]
ms.assetid: c0f7ae92-eeec-430e-a66a-f22c3ae64a5e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7886a9a6f51c76ed693576ca6f4659f4051d1f20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725355"
---
# <a name="filtering-values-using-sqllimit-field-and-sqllimit-value-sqlxml-40"></a><span data-ttu-id="eea7c-102">Filtrare valori tramite sql:limit-field e sql:limit-value (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="eea7c-102">Filtering Values Using sql:limit-field and sql:limit-value (SQLXML 4.0)</span></span>
  <span data-ttu-id="eea7c-103">È possibile limitare le righe restituite da una query di database in base a un valore di limitazione.</span><span class="sxs-lookup"><span data-stu-id="eea7c-103">You can limit rows that are returned from a database query on the basis of some limiting value.</span></span> <span data-ttu-id="eea7c-104">Le annotazioni `sql:limit-field` e `sql:limit-value` vengono utilizzate per identificare la colonna di database che contiene valori di limitazione e per specificare un valore di limitazione specifico da utilizzare per filtrare i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="eea7c-104">The `sql:limit-field` and `sql:limit-value` annotations are used to identify the database column that contains limiting values and to specify a specific limiting value to be used to filter the data returned.</span></span>  
  
 <span data-ttu-id="eea7c-105">L'annotazione `sql:limit-field` viene utilizzata per identificare una colonna che contiene un valore di limitazione ed è consentita in ciascun elemento o attributo di cui sia stato eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="eea7c-105">The `sql:limit-field` annotation is used to identify a column that contains a limiting value; it is allowed on each mapped element or attribute.</span></span>  
  
 <span data-ttu-id="eea7c-106">L'annotazione `sql:limit-value` viene utilizzata per specificare il valore limitato nella colonna specificata nell'annotazione `sql:limit-field`.</span><span class="sxs-lookup"><span data-stu-id="eea7c-106">The `sql:limit-value` annotation is used to specify the limited value in the column that is specified in the `sql:limit-field` annotation.</span></span> <span data-ttu-id="eea7c-107">L'annotazione `sql:limit-value` è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="eea7c-107">The `sql:limit-value` annotation is optional.</span></span> <span data-ttu-id="eea7c-108">Se l'annotazione `sql:limit-value` non viene specificata, si presuppone un valore NULL.</span><span class="sxs-lookup"><span data-stu-id="eea7c-108">If `sql:limit-value` is not specified, a NULL value is assumed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eea7c-109">Quando si utilizza un'annotazione `sql:limit-field` in cui la colonna SQL mappata è di tipo `real`, SQLXML 4.0 esegue la conversione nell'annotazione `sql:limit-value` specificata negli elementi XML Schema come valore `nvarchar` specificato.</span><span class="sxs-lookup"><span data-stu-id="eea7c-109">When working with a `sql:limit-field` where the mapped SQL column is of type `real`, SQLXML 4.0 performs conversion on the `sql:limit-value` as specified in XML schemas as an `nvarchar` specified value.</span></span> <span data-ttu-id="eea7c-110">Per questa operazione è necessario che i valori del limite decimale siano specificati tramite la notazione scientifica completa.</span><span class="sxs-lookup"><span data-stu-id="eea7c-110">This requires that decimal limit values be specified using full scientific notation.</span></span> <span data-ttu-id="eea7c-111">Per ulteriori informazioni, vedere l'esempio B seguente.</span><span class="sxs-lookup"><span data-stu-id="eea7c-111">For more information, see Example B below.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="eea7c-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="eea7c-112">Examples</span></span>  
 <span data-ttu-id="eea7c-113">Per creare esempi reali utilizzando questi esempi, è necessario che siano installati gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="eea7c-113">To create working samples using these examples, you need to have the following installed:</span></span>  
  
-   <span data-ttu-id="eea7c-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="eea7c-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="eea7c-115">MDAC 2.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="eea7c-115">MDAC 2.6 or later</span></span>  
  
 <span data-ttu-id="eea7c-116">In questi esempi vengono utilizzati modelli per specificare query XPath sullo schema di mapping XSD.</span><span class="sxs-lookup"><span data-stu-id="eea7c-116">In these examples, templates are used to specify XPath queries against the mapping XSD schema.</span></span>  
  
### <a name="a-limiting-the-customer-addresses-returned-to-a-specific-address-type"></a><span data-ttu-id="eea7c-117">R.</span><span class="sxs-lookup"><span data-stu-id="eea7c-117">A.</span></span> <span data-ttu-id="eea7c-118">Limitazione degli indirizzi dei clienti restituiti a un tipo di indirizzo specifico</span><span class="sxs-lookup"><span data-stu-id="eea7c-118">Limiting the customer addresses returned to a specific address type</span></span>  
 <span data-ttu-id="eea7c-119">In questo esempio un database contiene due tabelle:</span><span class="sxs-lookup"><span data-stu-id="eea7c-119">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="eea7c-120">Customer (CustomerID, CompanyName)</span><span class="sxs-lookup"><span data-stu-id="eea7c-120">Customer (CustomerID, CompanyName)</span></span>  
  
-   <span data-ttu-id="eea7c-121">Addresses (CustomerID, AddressType, StreetAddress)</span><span class="sxs-lookup"><span data-stu-id="eea7c-121">Addresses (CustomerID, AddressType, StreetAddress)</span></span>  
  
 <span data-ttu-id="eea7c-122">Un cliente può disporre di un indirizzo di spedizione e/o di un indirizzo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="eea7c-122">A customer can have a shipping address and/or a billing address.</span></span> <span data-ttu-id="eea7c-123">I valori della colonna AddressType sono Shipping e Billing.</span><span class="sxs-lookup"><span data-stu-id="eea7c-123">The AddressType column values are Shipping and Billing.</span></span>  
  
 <span data-ttu-id="eea7c-124">Si tratta dello schema di mapping in cui l'attributo dello schema **ShipTo** viene mappato alla colonna StreetAddress nella relazione degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="eea7c-124">This is the mapping schema in which the **ShipTo** schema attribute maps to the StreetAddress column in the Addresses relation.</span></span> <span data-ttu-id="eea7c-125">I valori restituiti per questo attributo vengono limitati solo agli indirizzi di spedizione specificando le annotazioni `sql:limit-field` e `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="eea7c-125">The values that are returned for this attribute are limited to only shipping addresses by specifying the `sql:limit-field` and `sql:limit-value` annotations.</span></span> <span data-ttu-id="eea7c-126">Analogamente, l'attributo dello schema **billTo** restituisce solo l'indirizzo di fatturazione di un cliente.</span><span class="sxs-lookup"><span data-stu-id="eea7c-126">Similarly, the **BillTo** schema attribute returns only the billing address of a customer.</span></span>  
  
 <span data-ttu-id="eea7c-127">Lo schema è il seguente:</span><span class="sxs-lookup"><span data-stu-id="eea7c-127">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustAddr"  
        parent="Customer"  
        parent-key="CustomerID"  
        child="Addresses"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Customer" >  
   <xsd:complexType>  
        <xsd:sequence>  
        <xsd:element name="BillTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="billing"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        <xsd:element name="ShipTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="shipping"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:int" />   
        <xsd:attribute name="CompanyName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="eea7c-128">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="eea7c-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="eea7c-129">Creare due tabelle nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eea7c-129">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (CustomerID int primary key,   
                           CompanyName varchar(30))  
    CREATE TABLE Addresses(CustomerID int,   
                           StreetAddress varchar(50),  
                           AddressType varchar(10))  
    ```  
  
2.  <span data-ttu-id="eea7c-130">Aggiungere i dati di esempio:</span><span class="sxs-lookup"><span data-stu-id="eea7c-130">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Customer values (1, 'Company A')  
    INSERT INTO Customer values (2, 'Company B')  
  
    INSERT INTO Addresses values  
               (1, 'Obere Str. 57 Berlin', 'billing')  
    INSERT INTO Addresses values  
               (1, 'Avda. de la Constituci??n 2222 M??xico D.F.', 'shipping')  
    INSERT INTO Addresses values  
               (2, '120 Hanover Sq., London', 'billing')  
    INSERT INTO Addresses values  
               (2, 'Forsterstr. 57, Mannheim', 'shipping')  
    ```  
  
3.  <span data-ttu-id="eea7c-131">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="eea7c-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="eea7c-132">Salvare il file con il nome LimitFieldValue.xml.</span><span class="sxs-lookup"><span data-stu-id="eea7c-132">Save the file as LimitFieldValue.xml.</span></span>  
  
4.  <span data-ttu-id="eea7c-133">Creare il modello seguente (LimitFieldValueT.xml) e salvarlo nello stesso percorso in cui è stato salvato lo schema (LimitFieldValue.xml) nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="eea7c-133">Create the following template (LimitFieldValueT.xml), and save it in the same where you saved the schema (LimitFieldValue.xml) in the previous step:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="LimitFieldValue.xml">  
            /Customer  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="eea7c-134">Il percorso di directory specificato per lo schema di mapping (LimitFieldValue.xml) è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="eea7c-134">The directory path specified for the mapping schema (LimitFieldValue.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="eea7c-135">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eea7c-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\LimitFieldValue.xml"  
    ```  
  
5.  <span data-ttu-id="eea7c-136">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="eea7c-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="eea7c-137">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="eea7c-137">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="eea7c-138">Risultato:</span><span class="sxs-lookup"><span data-stu-id="eea7c-138">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1" CompanyName="Company A">   
     <BillTo>Obere Str. 57 Berlin</BillTo>   
     <ShipTo>Avda. de la Constituci??n 2222 M??xico D.F.</ShipTo>   
  </Customer>   
  <Customer CustomerID="2" CompanyName="Company B">   
     <BillTo>120 Hanover Sq., London</BillTo>   
     <ShipTo>Forsterstr. 57, Mannheim</ShipTo>   
   </Customer>   
</ROOT>  
```  
  
### <a name="b-limiting-results-based-on-a-discount-value-of-type-real-data"></a><span data-ttu-id="eea7c-139">B.</span><span class="sxs-lookup"><span data-stu-id="eea7c-139">B.</span></span> <span data-ttu-id="eea7c-140">Limitare i risultati in base a un valore di sconto con tipo di dati real</span><span class="sxs-lookup"><span data-stu-id="eea7c-140">Limiting results based on a discount value of type real data</span></span>  
 <span data-ttu-id="eea7c-141">In questo esempio un database contiene due tabelle:</span><span class="sxs-lookup"><span data-stu-id="eea7c-141">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="eea7c-142">Orders (OrderID)</span><span class="sxs-lookup"><span data-stu-id="eea7c-142">Orders (OrderID)</span></span>  
  
-   <span data-ttu-id="eea7c-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span><span class="sxs-lookup"><span data-stu-id="eea7c-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span></span>  
  
 <span data-ttu-id="eea7c-144">Si tratta dello schema di mapping in cui l'attributo **OrderID** sui dettagli dell'ordine viene mappato alla colonna OrderID nella relazione Orders.</span><span class="sxs-lookup"><span data-stu-id="eea7c-144">This is the mapping schema in which the **OrderID** attribute on the order details maps to the OrderID column in the orders relation.</span></span> <span data-ttu-id="eea7c-145">I valori restituiti per questo attributo sono limitati solo a quelli con valore pari 2.0000000 e-001 (0,2) come specificato per l'attributo **discount** usando le `sql:limit-field` `sql:limit-value` annotazioni e.</span><span class="sxs-lookup"><span data-stu-id="eea7c-145">The values that are returned for this attribute are limited to only those that have a value of 2.0000000e-001 (0.2) as specified for the **Discount** attribute using the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 <span data-ttu-id="eea7c-146">Lo schema è il seguente:</span><span class="sxs-lookup"><span data-stu-id="eea7c-146">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
   <xsd:appinfo>  
    <sql:relationship name="OrderOrderDetails"  
        parent="Orders"  
        parent-key="OrderID"  
        child="OrderDetails"  
        child-key="OrderID" />  
   </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="root" sql:is-constant="1">  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="Order" sql:relation="Orders" >  
          <xsd:complexType>  
             <xsd:sequence>  
                <xsd:element name="orderDetail"   
                       sql:relation="OrderDetails"   
                       sql:limit-field="Discount"                       sql:limit-value="2.0000000e-001"  
                       sql:relationship="OrderOrderDetails">  
                   <xsd:complexType>  
                     <xsd:attribute name="OrderID"   />   
                     <xsd:attribute name="ProductID" />   
                     <xsd:attribute name="Discount"  />   
                     <xsd:attribute name="Quantity"  />   
                     <xsd:attribute name="UnitPrice" />   
                   </xsd:complexType>  
                </xsd:element>  
            </xsd:sequence>  
           <xsd:attribute name="OrderID"/>   
          </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="eea7c-147">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="eea7c-147">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="eea7c-148">Creare due tabelle nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eea7c-148">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Orders ([OrderID] int NOT NULL ) ON [PRIMARY]  
    ALTER TABLE Orders WITH NOCHECK ADD   
    CONSTRAINT [PK_Orders] PRIMARY KEY  CLUSTERED (  
       [OrderID]  
     )  ON [PRIMARY]   
    CREATE TABLE [OrderDetails] (  
       [OrderID] int NOT NULL ,  
       [ProductID] int NOT NULL ,  
       [UnitPrice] money NULL ,  
       [Quantity] smallint NOT NULL ,  
       [Discount] real NOT NULL   
    ) ON [PRIMARY]  
    ```  
  
2.  <span data-ttu-id="eea7c-149">Aggiungere i dati di esempio:</span><span class="sxs-lookup"><span data-stu-id="eea7c-149">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Orders ([OrderID]) values (10248)  
    INSERT INTO Orders ([OrderID]) values (10250)  
    INSERT INTO Orders ([OrderID]) values (10251)  
    INSERT INTO Orders ([OrderID]) values (10257)  
    INSERT INTO Orders ([OrderID]) values (10258)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10248,11,14,12,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10250,51,42.4,35,0.15)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10251,22,16.8,6,0.05)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10257,77,10.4,15,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10258,2,15.2,50,0.2)  
    ```  
  
3.  <span data-ttu-id="eea7c-150">Salvare lo schema (LimitFieldValue.xml) in una directory.</span><span class="sxs-lookup"><span data-stu-id="eea7c-150">Save the schema (LimitFieldValue.xml) in a directory.</span></span>  
  
4.  <span data-ttu-id="eea7c-151">Creare lo script di test seguente (TestQuery.vbs), modificare MyServer nel nome del computer SQL Server e salvarlo nella stessa directory utilizzata nel passaggio precedente per salvare lo schema:</span><span class="sxs-lookup"><span data-stu-id="eea7c-151">Create the following test script (TestQuery.vbs), modify MyServer to the name of your SQL Server computer and save it in the same directory as you used in the previous step to save the schema:</span></span>  
  
    ```  
    Set conn = CreateObject("ADODB.Connection")  
    conn.Open "Provider=SQLOLEDB;Data Source=MyServer;Database=tempdb;Integrated Security=SSPI"  
    conn.Properties("SQLXML Version") = "sqlxml.4.0"   
    Set cmd = CreateObject("ADODB.Command")  
    Set stm = CreateObject("ADODB.Stream")  
    Set cmd.ActiveConnection = conn  
    stm.open  
    result ="none"  
    strXPathQuery="/root"  
    DBGUID_XPATH = "{EC2A4293-E898-11D2-B1B7-00C04F680C56}"  
    cmd.Dialect = DBGUID_XPATH  
    cmd.CommandText = strXPathQuery  
    cmd.Properties("Mapping schema") = "LimitFieldReal.xml"  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    WScript.Echo "executing for xml query"  
    On Error Resume Next  
    cmd.Execute , ,1024  
    if err then  
    Wscript.Echo err.description  
    Wscript.Echo err.Number  
    Wscript.Echo err.source  
    On Error GoTo 0  
    else  
    stm.Position = 0  
    result  = stm.ReadText  
    end if  
    WScript.Echo result  
    Wscript.Echo "done"  
    ```  
  
5.  <span data-ttu-id="eea7c-152">Eseguire il file TestQuery.vbs facendovi clic sopra in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="eea7c-152">Execute the TestQuery.vbs file by clicking on it in Windows Explorer.</span></span>  
  
     <span data-ttu-id="eea7c-153">Risultato:</span><span class="sxs-lookup"><span data-stu-id="eea7c-153">This is the result:</span></span>  
  
    ```  
    <root>  
      <Order OrderID="10248"/>  
      <Order OrderID="10250"/>  
      <Order OrderID="10251"/>  
      <Order OrderID="10257"/>  
      <Order OrderID="10258">  
        <orderDetail OrderID="10258"   
                     ProductID="2"   
                     Discount="0.2"   
                     Quantity="50"/>  
      </Order>  
    </root>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eea7c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eea7c-154">See Also</span></span>  
 <span data-ttu-id="eea7c-155">[&#41;Transact-SQL float e Real &#40;](/sql/t-sql/data-types/float-and-real-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eea7c-155">[float and real &#40;Transact-SQL&#41;](/sql/t-sql/data-types/float-and-real-transact-sql) </span></span>  
 <span data-ttu-id="eea7c-156">[nchar e nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eea7c-156">[nchar and nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span></span>  
 <span data-ttu-id="eea7c-157">[Installazione di SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span><span class="sxs-lookup"><span data-stu-id="eea7c-157">[Installing SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span></span>  
 [<span data-ttu-id="eea7c-158">Utilizzo di schemi XSD con annotazioni nelle query &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="eea7c-158">Using Annotated XSD Schemas in Queries &#40;SQLXML 4.0&#41;</span></span>](../../relational-databases/sqlxml/annotated-xsd-schemas/using-annotated-xsd-schemas-in-queries-sqlxml-4-0.md)  
  
  
