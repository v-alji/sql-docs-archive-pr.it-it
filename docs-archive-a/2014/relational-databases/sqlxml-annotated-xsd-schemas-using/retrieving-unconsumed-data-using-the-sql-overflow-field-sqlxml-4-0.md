---
title: 'Recupero di dati non utilizzati tramite SQL: overflow-field (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- unconsumed data
- storing unconsumed data
- retrieving unconsumed data
- annotated XSD schemas, unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: 8526998d-b47d-4a32-8dc2-7f50a8d11097
author: rothja
ms.author: jroth
ms.openlocfilehash: 796fda9428954c5f18c5d37b353de9fd4122551e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636636"
---
# <a name="retrieving-unconsumed-data-using-the-sqloverflow-field-sqlxml-40"></a><span data-ttu-id="22f66-102">Recupero di dati non utilizzati mediante sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="22f66-102">Retrieving Unconsumed Data Using the sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="22f66-103">Quando i record vengono inseriti in un database da un documento XML tramite la funzione OPENXML [!INCLUDE[tsql](../../includes/tsql-md.md)], tutti i dati non utilizzati dal documento XML di origine possono essere archiviati in una colonna.</span><span class="sxs-lookup"><span data-stu-id="22f66-103">When records are inserted in a database from an XML document by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML function, all the unconsumed data from the source XML document can be stored in a column.</span></span> <span data-ttu-id="22f66-104">Quando si recuperano dati da un database tramite schemi con annotazioni, è possibile specificare l'attributo `sql:overflow-field` per identificare la colonna nella tabella nella quale vengono archiviati i dati di overflow.</span><span class="sxs-lookup"><span data-stu-id="22f66-104">When you retrieve data from a database by using annotated schemas, you can specify the `sql:overflow-field` attribute to identify the column in the table in which the overflow data is stored.</span></span> <span data-ttu-id="22f66-105">L' `sql:overflow-field` attributo può essere specificato in **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="22f66-105">The `sql:overflow-field` attribute can be specified on **\<element>**.</span></span>  
  
 <span data-ttu-id="22f66-106">I dati vengono quindi recuperati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22f66-106">This data is then retrieved in these ways:</span></span>  
  
-   <span data-ttu-id="22f66-107">Gli attributi archiviati nella colonna di overflow vengono aggiunti all'elemento che contiene l'annotazione `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="22f66-107">Attributes stored in the overflow column are added to the element that contains the `sql:overflow-field` annotation.</span></span>  
  
-   <span data-ttu-id="22f66-108">Gli elementi figlio e i relativi discendenti, archiviati nella colonna di overflow nel database, vengono aggiunti come elementi figlio dopo il contenuto specificato in modo esplicito nello schema.</span><span class="sxs-lookup"><span data-stu-id="22f66-108">The child elements and their descendents, stored in the overflow column in the database, are added as child elements following the content that is explicitly specified in the schema.</span></span> <span data-ttu-id="22f66-109">Non viene rispettato alcun ordine.</span><span class="sxs-lookup"><span data-stu-id="22f66-109">(No order is preserved.)</span></span>  
  
## <a name="examples"></a><span data-ttu-id="22f66-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="22f66-110">Examples</span></span>  
 <span data-ttu-id="22f66-111">Per creare esempi reali utilizzando gli esempi seguenti, è necessario soddisfare alcuni requisiti.</span><span class="sxs-lookup"><span data-stu-id="22f66-111">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="22f66-112">Per ulteriori informazioni, vedere [requisiti per l'esecuzione di esempi SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="22f66-112">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqloverflow-field-for-an-element"></a><span data-ttu-id="22f66-113">R.</span><span class="sxs-lookup"><span data-stu-id="22f66-113">A.</span></span> <span data-ttu-id="22f66-114">Specifica di sql:overflow-field per un elemento</span><span class="sxs-lookup"><span data-stu-id="22f66-114">Specifying sql:overflow-field for an element</span></span>  
 <span data-ttu-id="22f66-115">In questo esempio si presuppone che sia stato eseguito lo script seguente per far sì che una tabella denominata Customers2 esista nel database tempdb:</span><span class="sxs-lookup"><span data-stu-id="22f66-115">This example assumes that the following script has been run so that a table named Customers2 exists in the tempdb database:</span></span>  
  
```  
USE tempdb  
CREATE TABLE Customers2 (  
CustomerID       VARCHAR(10),   
ContactName    VARCHAR(30),   
AddressOverflow    NVARCHAR(500))  
  
GO  
INSERT INTO Customers2 VALUES (  
'ALFKI',   
'Joe',  
'<Address>  
  <Address1>Maple St.</Address1>  
  <Address2>Apt. E105</Address2>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98147</Zip>  
 </Address>')  
GO  
```  
  
 <span data-ttu-id="22f66-116">Inoltre, è necessario creare una directory virtuale per il database tempdb e un nome virtuale modello di `template` tipo denominato "template".</span><span class="sxs-lookup"><span data-stu-id="22f66-116">In addition, you must create a virtual directory for the tempdb database-and a template virtual name of `template` type named "template".</span></span>  
  
 <span data-ttu-id="22f66-117">Nell'esempio seguente lo schema di mapping recupera i dati non utilizzati archiviati nella colonna AddressOverflow della tabella Customers2:</span><span class="sxs-lookup"><span data-stu-id="22f66-117">In the following example, the mapping schema retrieves the unconsumed data that is stored in the AddressOverflow column of the Customers2 table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customers2" sql:overflow-field="AddressOverflow" >  
    <xsd:complexType>  
      <xsd:attribute name="CustomerID"  type="xsd:integer"/>  
      <xsd:attribute name="ContactName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="22f66-118">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="22f66-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="22f66-119">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="22f66-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="22f66-120">Salvare il file con il nome Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="22f66-120">Save the file as Overflow.xml.</span></span>  
  
2.  <span data-ttu-id="22f66-121">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="22f66-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="22f66-122">Salvare il file come OverflowT.xml nella stessa directory nella quale è stato salvato Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="22f66-122">Save the file as OverflowT.xml in the same directory where you saved Overflow.xml.</span></span> <span data-ttu-id="22f66-123">La query nel modello seleziona tutti i record nella tabella Customer2.</span><span class="sxs-lookup"><span data-stu-id="22f66-123">The query in the template selects the records in the Customers2 table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Overflow.xml">  
            /Customers2  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="22f66-124">Il percorso della directory specificato per lo schema di mapping (Overflow.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="22f66-124">The directory path specified for the mapping schema (Overflow.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="22f66-125">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="22f66-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\Overflow.xml"  
    ```  
  
3.  <span data-ttu-id="22f66-126">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="22f66-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="22f66-127">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="22f66-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="22f66-128">Set di risultati:</span><span class="sxs-lookup"><span data-stu-id="22f66-128">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers2 CustomerID="ALFKI" ContactName="Joe">  
    <Address1>Maple St.</Address1>   
    <Address2>Apt. E105</Address2>   
    <City>Seattle</City>   
    <State>WA</State>   
    <Zip>98147</Zip>   
  </Customers2>  
</ROOT>  
```  
  
  
