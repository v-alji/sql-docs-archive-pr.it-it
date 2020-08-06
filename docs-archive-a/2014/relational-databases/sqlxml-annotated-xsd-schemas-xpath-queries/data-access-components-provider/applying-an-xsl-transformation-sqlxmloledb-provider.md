---
title: Applicazione di una trasformazione XSL (provider SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, applying XSL transformations
- applying XSL transformations [SQLXML]
- xsl property
- Base Path property
- XSL Transformations [SQLXML]
ms.assetid: cb5e41ab-dd20-4873-af20-f417bd1bbf6d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fbb427a95d9f2308bf65724758a4a1563b42575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629742"
---
# <a name="applying-an-xsl-transformation-sqlxmloledb-provider"></a><span data-ttu-id="8e8e3-102">Applicazione di una trasformazione XSL (provider SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="8e8e3-102">Applying an XSL Transformation (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="8e8e3-103">In questa applicazione ADO di esempio viene eseguita una query SQL e viene applicata una trasformazione XSL al risultato.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-103">In this sample ADO application, an SQL query is executed, and an XSL transformation is applied to the result.</span></span> <span data-ttu-id="8e8e3-104">L'impostazione della proprietà ClientSideXML su true impone l'elaborazione del set di righe sul lato client.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-104">Setting the ClientSideXML property to True enforces the processing of the rowset on the client side.</span></span> <span data-ttu-id="8e8e3-105">Il sottolinguaggio del comando è impostato su {5d531cb2-e6ed-11d2-b252-00c04f681b71}, in quanto la query SQL è specificata in un modello e questo sottolinguaggio deve essere specificato per l'esecuzione di un modello.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-105">The command dialect is set to {5d531cb2-e6ed-11d2-b252-00c04f681b71}, because the SQL query is specified in a template and this dialect must be specified when executing a template.</span></span> <span data-ttu-id="8e8e3-106">La proprietà XSL specifica il file XSL da usare per applicare la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-106">The xsl property specifies the XSL file to use to apply the transformation.</span></span> <span data-ttu-id="8e8e3-107">Il valore della proprietà percorso di base viene utilizzato per cercare il file XSL.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-107">The value of Base Path property is used to search for the XSL file.</span></span> <span data-ttu-id="8e8e3-108">Se si specifica un percorso nel valore della proprietà XSL, il percorso è relativo al percorso specificato nella proprietà del percorso di base.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-108">If you specify a path in the value of the xsl property, the path is relative to the path that is specified in the Base Path property.</span></span>  
  
 <span data-ttu-id="8e8e3-109">In questo esempio viene illustrato come utilizzare le proprietà specifiche del provider SQLXMLOLEDB seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e8e3-109">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="8e8e3-110">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="8e8e3-110">ClientSideXML</span></span>  
  
-   <span data-ttu-id="8e8e3-111">xsl</span><span class="sxs-lookup"><span data-stu-id="8e8e3-111">xsl</span></span>  
  
 <span data-ttu-id="8e8e3-112">In questa applicazione ADO di esempio sul lato client, viene eseguito un modello XML costituito da una query SQL nel server.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-112">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="8e8e3-113">Poiché la proprietà ClientSideXML è impostata su true, l'istruzione SELECT senza la clausola FOR XML viene inviata al server.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-113">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="8e8e3-114">Il server esegue la query e restituisce un set di righe al client.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-114">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="8e8e3-115">Il client applica quindi la trasformazione FOR XML al set di righe e produce il documento XML.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-115">The client then applies the FOR XML transformation to the rowset and produces the XML document.</span></span>  
  
 <span data-ttu-id="8e8e3-116">La proprietà XSL è specificata nell'applicazione. Pertanto, la trasformazione XSL viene applicata al documento XML generato nel client e il risultato è una tabella a due colonne.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-116">The xsl property is specified in the application; therefore, the XSL transformation is applied to the XML document that is generated on the client, and the result is a two-column table.</span></span>  
  
 <span data-ttu-id="8e8e3-117">Per eseguire il comando del modello, è necessario specificare il sottolinguaggio del modello XML ({5d531cb2-e6ed-11d2-b252-00c04f681b71}).</span><span class="sxs-lookup"><span data-stu-id="8e8e3-117">To execute the template command, the XML template dialect - {5d531cb2-e6ed-11d2-b252-00c04f681b71} - must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e8e3-118">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-118">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="8e8e3-119">In questo esempio viene inoltre specificato l'utilizzo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client come provider di dati, che richiede l'installazione di un software client di rete aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-119">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="8e8e3-120">Per ulteriori informazioni, vedere [requisiti di sistema per SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="8e8e3-120">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
Set oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = _  
        "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' >" & _  
       " <sql:query> " & _  
        "   SELECT TOP 25 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
oTestStream.Open  
' You need the dialect if you are executing a template.  
oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\ExecuteTemplateWithXSL\"  
oTestCommand.Properties("xsl").Value = "myxsl.xsl"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
 <span data-ttu-id="8e8e3-121">Di seguito viene fornito il modello XSL.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-121">The XSL template follows.</span></span> <span data-ttu-id="8e8e3-122">Il risultato dell'applicazione di questo modello XSL è una tabella a due colonne.</span><span class="sxs-lookup"><span data-stu-id="8e8e3-122">The result of applying this XSL template is a two-column table.</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>            
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
  
    <xsl:template match = 'Person.Contact'>  
       <TR>  
         <TD><xsl:value-of select = '@FirstName' /></TD>  
         <TD><B><xsl:value-of select = '@LastName' /></B></TD>  
       </TR>  
    </xsl:template>  
    <xsl:template match = '/'>  
      <HTML>  
        <HEAD>  
           <STYLE>th { background-color: #CCCCCC }</STYLE>  
        </HEAD>  
        <BODY>  
         <TABLE border='1' style='width:300;'>  
           <TR><TH colspan='2'>Contacts</TH></TR>  
           <TR>  
              <TH >First name</TH>  
              <TH>Last name</TH>  
           </TR>  
           <xsl:apply-templates select = 'ROOT' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
  
