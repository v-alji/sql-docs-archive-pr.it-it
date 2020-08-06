---
title: Esecuzione di modelli che contengono query XPath (provider SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing template files
- Base Path property
- templates [SQLXML], XPath queries
- XPath queries [SQLXML], templates
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
- XML templates [SQLXML]
ms.assetid: 7368c188-607e-459e-8254-8f23352dfa01
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d31c95fe5d4fb1b7dc9a8d039a56b41cdd7349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716159"
---
# <a name="executing-templates-that-contain-xpath-queries-sqlxmloledb-provider"></a><span data-ttu-id="91620-102">Esecuzione di modelli che contengono query XPath (provider SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="91620-102">Executing Templates That Contain XPath Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="91620-103">In questo esempio viene illustrato come utilizzare le proprietà specifiche del provider SQLXMLOLEDB seguenti:</span><span class="sxs-lookup"><span data-stu-id="91620-103">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="91620-104">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="91620-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="91620-105">Percorso di base</span><span class="sxs-lookup"><span data-stu-id="91620-105">Base Path</span></span>  
  
-   <span data-ttu-id="91620-106">Schema di mapping</span><span class="sxs-lookup"><span data-stu-id="91620-106">Mapping Schema</span></span>  
  
 <span data-ttu-id="91620-107">In questa applicazione ADO di esempio, un modello XML costituito da una query XPath (radice) viene specificato sullo schema di mapping XSD (MySchema.xml) descritto in [esecuzione di query xpath &#40;provider SQLXMLOLEDB&#41;](executing-xpath-queries-sqlxmloledb-provider.md).</span><span class="sxs-lookup"><span data-stu-id="91620-107">In this sample ADO application, an XML template that consists of an XPath query (root) is specified against the XSD mapping schema (MySchema.xml) that is described in [Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;](executing-xpath-queries-sqlxmloledb-provider.md).</span></span>  
  
 <span data-ttu-id="91620-108">La proprietà Schema di mapping fornisce lo schema di mapping XSD sul quale viene eseguita la query XPath.</span><span class="sxs-lookup"><span data-stu-id="91620-108">The Mapping Schema property provides the XSD mapping schema against which the XPath query is executed.</span></span> <span data-ttu-id="91620-109">La proprietà percorso di base fornisce il percorso del file allo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="91620-109">The Base Path property provides the file path to the mapping schema.</span></span>  
  
 <span data-ttu-id="91620-110">La proprietà ClientSideXML è impostata su true.</span><span class="sxs-lookup"><span data-stu-id="91620-110">The ClientSideXML property is set to True.</span></span> <span data-ttu-id="91620-111">pertanto il documento XML viene generato sul client.</span><span class="sxs-lookup"><span data-stu-id="91620-111">Therefore, the XML document is generated on the client.</span></span>  
  
 <span data-ttu-id="91620-112">Nell'applicazione viene specificata direttamente una query XPath</span><span class="sxs-lookup"><span data-stu-id="91620-112">In the application, an XPath query is specified directly.</span></span> <span data-ttu-id="91620-113">È pertanto necessario includere il sottolinguaggio {5d531cb2-e6ed-11d2-b252-00c04f681b71}.</span><span class="sxs-lookup"><span data-stu-id="91620-113">Therefore, the dialect {5d531cb2-e6ed-11d2-b252-00c04f681b71} must be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91620-114">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="91620-114">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="91620-115">In questo esempio viene inoltre specificato l'utilizzo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) per il provider di dati che richiede l'installazione di un software client di rete aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="91620-115">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="91620-116">Per ulteriori informazioni, vedere [requisiti di sistema per SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="91620-116">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub Main()  
  
   Dim oTestStream As New ADODB.Stream  
   Dim oTestConnection As New ADODB.Connection  
   Dim oTestCommand As New ADODB.Command  
  
   oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
  
   oTestCommand.ActiveConnection = oTestConnection  
   oTestCommand.Properties("ClientSideXML") = "False"  
  
   oTestCommand.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'> " & _  
        " <sql:xpath-query mapping-schema='mySchema.xml' > " & _  
        "   root " & _  
        "   </sql:xpath-query> " & _  
        " </ROOT> "  
   oTestStream.Open  
   ' You need the dialect if you are executing a template.  
   oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
   oTestCommand.Properties("Output Stream").Value = oTestStream  
   oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\TemplateWithXPath\"  
   oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
   oTestCommand.Properties("Output Encoding") = "utf-8"  
   oTestCommand.Execute , , adExecuteStream  
   oTestStream.Position = 0  
   oTestStream.Charset = "utf-8"  
   Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
  
Sub Form_Load()  
   Main  
End Sub  
```  
  
 <span data-ttu-id="91620-117">Lo schema è il seguente:</span><span class="sxs-lookup"><span data-stu-id="91620-117">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contact'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  
  <xsd:element name='Contact' sql:relation='Person.Contact'>  
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
  
