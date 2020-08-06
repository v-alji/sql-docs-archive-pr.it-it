---
title: Esecuzione di un updategram utilizzando ADO (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- ADO [SQLXML]
- updategrams [SQLXML], ADO
- executing updategrams [SQLXML]
ms.assetid: 78610ca0-f763-45fc-ac64-da5c192cc3e5
author: rothja
ms.author: jroth
ms.openlocfilehash: d8bc00406705e73eb6c9a4f2474ac1865344a8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635982"
---
# <a name="executing-an-updategram-by-using-ado-sqlxml-40"></a><span data-ttu-id="38488-102">Esecuzione di un updategram mediante ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="38488-102">Executing an Updategram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="38488-103">Questa applicazione [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic utilizza ADO per stabilire una connessione a un'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ed eseguire un updategram.</span><span class="sxs-lookup"><span data-stu-id="38488-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and execute an updategram.</span></span> <span data-ttu-id="38488-104">L'updategram aggiorna il cognome di un dipendente specifico.</span><span class="sxs-lookup"><span data-stu-id="38488-104">The updategram updates the last name of a specific employee.</span></span> <span data-ttu-id="38488-105">In questo esempio viene utilizzato il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="38488-105">This example uses the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="38488-106">In questa applicazione di esempio:</span><span class="sxs-lookup"><span data-stu-id="38488-106">In this sample application:</span></span>  
  
-   <span data-ttu-id="38488-107">Oggetto **conn** (**ADODB. Connessione**) stabilisce una connessione a un'istanza in esecuzione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in un computer server specifico.</span><span class="sxs-lookup"><span data-stu-id="38488-107">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on a specific server computer.</span></span>  
  
-   <span data-ttu-id="38488-108">L'oggetto **cmd** (**ADODB. Command**) viene eseguito sulla connessione stabilita.</span><span class="sxs-lookup"><span data-stu-id="38488-108">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="38488-109">Il sottolinguaggio del comando viene impostato su DBGUID_MSSQLXML.</span><span class="sxs-lookup"><span data-stu-id="38488-109">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="38488-110">L'updategram viene copiato nel flusso di comandi (**strmIn**).</span><span class="sxs-lookup"><span data-stu-id="38488-110">The updategram is copied to the command stream (**strmIn**).</span></span>  
  
-   <span data-ttu-id="38488-111">Il flusso di output del comando è impostato sull'oggetto **StrmOut** (**ADODB. Stream**) per ricevere i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="38488-111">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="38488-112">Il comando (updategram) viene infine eseguito.</span><span class="sxs-lookup"><span data-stu-id="38488-112">Finally the command (updategram) is executed.</span></span>  
  
 <span data-ttu-id="38488-113">Di seguito viene riportato il codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="38488-113">Here is the sample code:</span></span>  
  
```vb  
Private Sub Form_Load()  
  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmIn As New ADODB.Stream  
  Dim strmOut As New ADODB.Stream  
  Dim SQLxml As String  
  
  ' Open a connection to the instance of SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=(local); database=AdventureWorks; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  
  ' Build the command string in the form of an XML template.  
    SQLxml = "<ROOT xmlns:updg='urn:schemas-microsoft-com:xml-updategram' >"  
    SQLxml = SQLxml & "  <updg:sync updg:nullvalue='IsNULL'>"  
    SQLxml = SQLxml & "    <updg:before>"  
    SQLxml = SQLxml & "       <Person.Contact ContactID='64' Title='IsNULL'/>"  
    SQLxml = SQLxml & "    </updg:before>"  
    SQLxml = SQLxml & "    <updg:after>"  
    SQLxml = SQLxml & "       <Person.Contact ContactID='64' Title='Mr.'/>"  
    SQLxml = SQLxml & "    </updg:after>"  
    SQLxml = SQLxml & "  </updg:sync>"  
    SQLxml = SQLxml & "</ROOT>"  
  
  ' Set the command dialect to DBGUID_MSSQLXML.  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
  ' Open the command stream and write our template to it.  
  strmIn.Open  
  strmIn.WriteText SQLxml  
  strmIn.Position = 0  
  
  Set cmd.CommandStream = strmIn  
  
  ' Execute the command, open the return stream, and read the result.  
  strmOut.Open  
  strmOut.LineSeparator = adCRLF  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Debug.Print strmOut.ReadText  
  strmOut.Close  
  strmIn.Close  
  
End Sub  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="38488-114">Se si utilizza SQLXML da ADO per eseguire gli updategram che specificano uno schema XSD, è necessario impostare la proprietà "`SQLXML Version`" su "`SQLXML.4.0`" sull'oggetto connection, come mostrato nella riga di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="38488-114">If you're using SQLXML from ADO to execute updategrams that specify an XSD schema, you must set the "`SQLXML Version`" property to "`SQLXML.4.0`" on the connection object, as shown in the following example line of code:</span></span>  
>   
>  `conn.Properties("SQLXML Version") = "SQLXML.4.0"`  
  
## <a name="specifying-a-mapping-schema-for-the-updategram"></a><span data-ttu-id="38488-115">Specifica di uno schema di mapping per l'updategram</span><span class="sxs-lookup"><span data-stu-id="38488-115">Specifying a Mapping Schema for the Updategram</span></span>  
 <span data-ttu-id="38488-116">In questo esempio viene illustrato come specificare e utilizzare uno schema di mapping in un updategram.</span><span class="sxs-lookup"><span data-stu-id="38488-116">This example illustrates how to specify and use a mapping schema in an updategram.</span></span>  
  
 <span data-ttu-id="38488-117">Salvare lo schema XSD seguente (EmpSchema.xml) sul disco e assicurarsi di aggiornare il percorso specificato nel codice nel percorso dello schema di mapping sul disco.</span><span class="sxs-lookup"><span data-stu-id="38488-117">Save the following XSD schema (EmpSchema.xml) to your disk, and be sure to update the path that is specified in the code to the location of the mapping schema on your disk.</span></span> <span data-ttu-id="38488-118">Il codice presuppone che lo schema venga salvato nell'unità C: nella cartella degli schemi.</span><span class="sxs-lookup"><span data-stu-id="38488-118">The code assumes that the schema is saved on the C: drive in the Schemas folder.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
        <xsd:attribute name="CID"    
                       sql:field="ContactID"   
                       type="xsd:string" />   
        <xsd:attribute name="MName"    
                       sql:field="MiddleName"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="38488-119">Dal momento che è possibile specificare sia gli schemi XSD sia gli schemi XDR, questo è lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="38488-119">Because both XSD and XDR schemas can be specified, this is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Contact" sql:relation="Person.Contact" >  
       <AttributeType name="CID" />  
       <AttributeType name="MName" />  
  
       <attribute type="CID" sql:field="ContactID" />  
       <attribute type="MName" sql:field="MiddleName" />  
     </ElementType>  
   </Schema>   
```  
  
 <span data-ttu-id="38488-120">Si tratta del codice di Visual Basic per l'esecuzione di un updategram al quale è associato uno schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="38488-120">This is the Visual Basic code to execute an updategram that has an associated mapping schema.</span></span> <span data-ttu-id="38488-121">L'updategram aggiorna il secondo nome per il contatto 1 nella tabella Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="38488-121">The updategram updates the middle name for contact 1 in the Person.Contact table.</span></span>  
  
```vb  
Private Sub Form_Load()  
    Dim cmd As New ADODB.Command  
    Dim conn As New ADODB.Connection  
    Dim strmIn As New ADODB.Stream  
    Dim strmOut As New ADODB.Stream  
  
    ' Open a connection to the SQL Server.  
    conn.Provider = "SQLOLEDB"  
    conn.Open "server=(local); database=AdventureWorks; Integrated Security='SSPI' ;"  
    conn.Properties("SQLXML Version") = "SQLXML.4.0"  
    Set cmd.ActiveConnection = conn  
  
    ' Open the command stream and write the template to it.  
    strmIn.Open  
    strmIn.WriteText "<ROOT xmlns:updg='urn:schemas-microsoft-com:xml-updategram' >"  
    strmIn.WriteText "  <updg:sync mapping-schema='C:\Schemas\EmpSchema.xml' >"  
    strmIn.WriteText "      <updg:before>"  
    strmIn.WriteText "          <Contact CID='1' />"  
    strmIn.WriteText "      </updg:before>"  
    strmIn.WriteText "      <updg:after>"  
    strmIn.WriteText "          <Contact MName='M.'/>"  
    strmIn.WriteText "      </updg:after>"  
    strmIn.WriteText "  </updg:sync>"  
    strmIn.WriteText "</ROOT>"  
  
    ' Set the command dialect to XML.  
    cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
    strmIn.Position = 0  
    Set cmd.CommandStream = strmIn  
  
    ' Execute the command, open the return stream, and read the result.  
    strmOut.Open  
    strmOut.LineSeparator = adCRLF  
    cmd.Properties("Output Stream").Value = strmOut  
    cmd.Execute , , adExecuteStream  
    strmOut.Position = 0  
    Debug.Print strmOut.ReadText  
    strmOut.Close  
    strmIn.Close  
    conn.Close  
End Sub  
```  
  
## <a name="passing-parameters"></a><span data-ttu-id="38488-122">Passaggio di parametri</span><span class="sxs-lookup"><span data-stu-id="38488-122">Passing Parameters</span></span>  
 <span data-ttu-id="38488-123">Nelle applicazioni Visual Basic fornite precedentemente i parametri non vengono passati.</span><span class="sxs-lookup"><span data-stu-id="38488-123">In the Visual Basic applications provided earlier, parameters are not passed.</span></span> <span data-ttu-id="38488-124">In questa applicazione i valori **ContactID** e **MiddleName** vengono passati come input con parametri all'updategram.</span><span class="sxs-lookup"><span data-stu-id="38488-124">In this application, the **ContactID** and **MiddleName** values are passed as parameterized input to the updategram.</span></span>  
  
```vb  
Private Sub Form_Load()  
  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmIn As New ADODB.Stream  
  Dim strmOut As New ADODB.Stream  
  Dim InputContactID As String  
  Dim InputMiddleName As String  
  
  InputContactID = "1"  
  InputMiddleName = "Q."  
  
  ' Open a connection to the instance of SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=(local); database=AdventureWorks; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  
  ' Build the command string in the form of an XML template.  
  SQLxml = "<ROOT xmlns:updg='urn:schemas-microsoft-com:xml-updategram' >"  
  SQLxml = SQLxml & "<updg:header>"  
  SQLxml = SQLxml & "<updg:param name='ContactID'/>"  
  SQLxml = SQLxml & "<updg:param name='MiddleName' />"  
  SQLxml = SQLxml & "</updg:header>"  
  SQLxml = SQLxml & "<updg:sync >"  
  SQLxml = SQLxml & " <updg:before>"  
  SQLxml = SQLxml & "   <Person.Contact ContactID='$ContactID' />"  
  SQLxml = SQLxml & "</updg:before>"  
  SQLxml = SQLxml & "<updg:after>"  
  SQLxml = SQLxml & "<Person.Contact MiddleName='$MiddleName' />"  
  SQLxml = SQLxml & "</updg:after>"  
  SQLxml = SQLxml & "</updg:sync>"  
  SQLxml = SQLxml & "</ROOT>"  
  
  ' Set the command dialect to XML.  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
  ' Open the command stream and write the template to it.  
  strmIn.Open  
  strmIn.WriteText SQLxml  
  strmIn.Position = 0  
  
  Set cmd.CommandStream = strmIn  
  
  ' Execute the command, open the return stream, and read the result.  
  strmOut.Open  
  strmOut.LineSeparator = adCRLF  
  cmd.NamedParameters = True  
  cmd.Parameters.Append cmd.CreateParameter("@ContactID", adBSTR, adParamInput, 1, InputContactID)  
  cmd.Parameters.Append cmd.CreateParameter("@MiddleName", adBSTR, adParamInput, 7, InputMiddleName)  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Debug.Print strmOut.ReadText  
  
End Sub  
```  
  
  
