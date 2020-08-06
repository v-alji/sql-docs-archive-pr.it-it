---
title: 'SQL: overflow-field (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: f005182b-6151-432d-ab22-3bc025742cd3
author: rothja
ms.author: jroth
ms.openlocfilehash: ea52eb642964844a03304d082632c2b7157f723b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634968"
---
# <a name="sqloverflow-field-sqlxml-40"></a><span data-ttu-id="588ea-102">sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="588ea-102">sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="588ea-103">In uno schema è possibile identificare una colonna come colonna di overflow per ricevere tutti i dati non utilizzati dal documento XML.</span><span class="sxs-lookup"><span data-stu-id="588ea-103">In a schema, you can identify a column as an overflow column to receive all unconsumed data from the XML document.</span></span> <span data-ttu-id="588ea-104">Questa colonna viene specificata nello schema mediante l'annotazione `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="588ea-104">This column is specified in the schema by using the `sql:overflow-field` annotation.</span></span> <span data-ttu-id="588ea-105">È possibile avere più colonne di overflow.</span><span class="sxs-lookup"><span data-stu-id="588ea-105">It is possible to have multiple overflow columns.</span></span>  
  
 <span data-ttu-id="588ea-106">Ogni volta che un nodo XML (elemento o attributo) per il quale è presente un'annotazione `sql:overflow-field` definita entra in ambito, la colonna di overflow viene attivata e riceve i dati non utilizzati.</span><span class="sxs-lookup"><span data-stu-id="588ea-106">Whenever an XML node (element or attribute) for which there is a `sql:overflow-field` annotation defined enters into scope, the overflow column is activated and receives unconsumed data.</span></span> <span data-ttu-id="588ea-107">Quando il nodo non è più in ambito, la colonna di overflow non è più attiva e il caricamento bulk XML rende attivo il campo di overflow precedente, se presente.</span><span class="sxs-lookup"><span data-stu-id="588ea-107">When the node goes out of scope, the overflow column is no longer active and XML Bulk Load makes the previous overflow field (if any) active.</span></span>  
  
 <span data-ttu-id="588ea-108">Dopo l'archiviazione dei dati nella colonna di overflow, il caricamento bulk XML archivia anche i tag di apertura e di chiusura dell'elemento padre per il quale viene definito `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="588ea-108">As it stores data in the overflow column, XML Bulk Load also stores the opening and closing tags of the parent element for which `sql:overflow-field` is defined.</span></span>  
  
 <span data-ttu-id="588ea-109">Lo schema seguente, ad esempio, descrive **\<Customers>** gli **\<CustOrder>** elementi e.</span><span class="sxs-lookup"><span data-stu-id="588ea-109">For example, the following schema describes the **\<Customers>** and **\<CustOrder>** elements.</span></span> <span data-ttu-id="588ea-110">Ognuno di questi elementi identifica una colonna di overflow:</span><span class="sxs-lookup"><span data-stu-id="588ea-110">Each of these elements identifies an overflow column:</span></span>  
  
```  
<?xml version="1.0" ?>  
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
 <xsd:element name="ROOT" sql:is-constant="1">  
  <xsd:complexType>  
    <xsd:sequence>   
      <xsd:element name="Customers"   
                   sql:relation="Cust"  
                   sql:overflow-field="OverflowColumn">  
        <xsd:complexType>  
             <xsd:sequence>   
             <xsd:element name="CustomerID" type="xsd:integer"/>  
             <xsd:element name="CompanyName"  type="xsd:string"/>  
             <xsd:element name="City" type="xsd:string"/>  
             <xsd:element name="Order"  
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder"  
                          sql:overflow-field="OverflowColumn">  
               <xsd:complexType>  
                 <xsd:attribute name="OrderID"/>  
                 <xsd:attribute name="CustomerID"/>  
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
  
 <span data-ttu-id="588ea-111">Nello schema viene eseguito il **\<Customer>** mapping dell'elemento alla tabella Cust e l' **\<Order>** elemento viene mappato alla tabella CustOrder.</span><span class="sxs-lookup"><span data-stu-id="588ea-111">In the schema, the **\<Customer>** element maps to the Cust table and the **\<Order>** element maps to the CustOrder table.</span></span>  
  
 <span data-ttu-id="588ea-112">Entrambi gli **\<Customer>** **\<Order>** elementi e identificano una colonna di overflow.</span><span class="sxs-lookup"><span data-stu-id="588ea-112">Both the **\<Customer>** and **\<Order>** elements identify an overflow column.</span></span> <span data-ttu-id="588ea-113">Pertanto, il caricamento bulk XML salva tutti gli attributi e gli elementi figlio non utilizzati dell' **\<Customer>** elemento nella colonna di overflow della tabella Cust e tutti gli attributi e gli elementi figlio non utilizzati dell' **\<Order>** elemento nella colonna di overflow della tabella CustOrder.</span><span class="sxs-lookup"><span data-stu-id="588ea-113">Thus, XML Bulk Load saves all the unconsumed child elements and attributes of the **\<Customer>** element in the overflow column of the Cust table, and all the unconsumed child elements and attributes of the **\<Order>** element in the overflow column of the CustOrder table.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="588ea-114">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="588ea-114">To test a working sample</span></span>  
  
1.  <span data-ttu-id="588ea-115">Salvare lo schema fornito in questo esempio come SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="588ea-115">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="588ea-116">Creare le tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="588ea-116">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
              CustomerID     int         PRIMARY KEY,  
              CompanyName    varchar(20) NOT NULL,  
              City           varchar(20) DEFAULT 'Seattle',  
              OverflowColumn nvarchar(200))  
    GO  
    CREATE TABLE CustOrder (  
              OrderID        int         PRIMARY KEY,  
              CustomerID     int         FOREIGN KEY REFERENCES  
                                              Cust(CustomerID),  
              OverflowColumn nvarchar(200))  
    GO  
    ```  
  
3.  <span data-ttu-id="588ea-117">Salvare i dati XML di esempio seguenti come file SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="588ea-117">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
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
       <City><![CDATA[LA]]> </City>  
       <xyz><address>111 Maple, Seattle</address></xyz>     
       <Order OrderID="3" />  
     </Customers>  
       <Customers>  
       <CustomerID>1113</CustomerID>  
       <CompanyName>Victuailles en stock</CompanyName>  
       <Order OrderID="4" />  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="588ea-118">Per eseguire il caricamento bulk XML, salvare ed eseguire questo esempio di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic, Scripting Edition (VBScript) come file Sample.vbs:</span><span class="sxs-lookup"><span data-stu-id="588ea-118">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
