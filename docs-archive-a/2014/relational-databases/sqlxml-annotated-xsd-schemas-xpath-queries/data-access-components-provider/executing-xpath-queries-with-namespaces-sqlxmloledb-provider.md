---
title: Esecuzione di query XPath con spazi dei nomi (provider SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- namespaces property
- queries [SQLXML], SQLXMLOLEDB Provider
- XPath queries [SQLXML], namespaces
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- namespaces [SQLXML], XPath queries
ms.assetid: 024a4b7d-435d-47ba-9e80-2c2f640108f5
author: rothja
ms.author: jroth
ms.openlocfilehash: ff692b49a4c32c14655af3a9eb07071dc60ba2a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716151"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxmloledb-provider"></a><span data-ttu-id="2ba84-102">Esecuzione di query XPath con spazi dei nomi (provider SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="2ba84-102">Executing XPath Queries with Namespaces (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="2ba84-103">Le query XPath possono includere spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ba84-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="2ba84-104">Se gli elementi dello schema sono spazi dei nomi qualificati, ovvero includono uno spazio dei nomi di destinazione, è necessario che nelle query XPath eseguite sullo schema sia specificato lo spazio dei nomi in questione.</span><span class="sxs-lookup"><span data-stu-id="2ba84-104">If the schema elements are namespace qualified (that is, if they include a target namespace), XPath queries against the schema must specify this namespace.</span></span>  
  
 <span data-ttu-id="2ba84-105">Poiché l'utilizzo del carattere jolly (\*) non è supportato in SQLXML 4.0, è necessario specificare la query XPath utilizzando un prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ba84-105">Because using the wildcard character (\*) is not supported in SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="2ba84-106">Per risolvere questo prefisso, utilizzare la proprietà Namespaces per specificare l'associazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ba84-106">To resolve this prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="2ba84-107">Nell'esempio seguente, la query XPath specifica gli spazi dei nomi usando il carattere jolly ( \* ) e le funzioni XPath local-name () e Namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="2ba84-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="2ba84-108">Questa query XPath restituisce tutti gli elementi in cui il nome locale è `Contact` e l'URI dello spazio dei nomi è `urn:myschema:Contacts`.</span><span class="sxs-lookup"><span data-stu-id="2ba84-108">This XPath query returns all the elements where the local name is `Contact` and the namespace URI is `urn:myschema:Contacts`.</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="2ba84-109">In SQLXML 4.0 questa query XPath deve essere specificata con un prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ba84-109">In SQLXML 4.0, this XPath query must be specified with a namespace prefix.</span></span> <span data-ttu-id="2ba84-110">Un esempio è costituito da `x:Contact`, dove `x` è il prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ba84-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="2ba84-111">Si consideri lo schema XSD seguente:</span><span class="sxs-lookup"><span data-stu-id="2ba84-111">Consider the following XSD schema:</span></span>  
  
```  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:con="urn:myschema:Contacts"  
            targetNamespace="urn:myschema:Contacts">  
<complexType name="ContactType">  
  <attribute name="CID" sql:field="ContactID" type="ID"/>  
  <attribute name="FName" sql:field="FirstName" type="string"/>  
  <attribute name="LName" sql:field="LastName"/>   
</complexType>  
<element name="Contact" type="con:ContactType" sql:relation="Person.Contact"/>  
</schema>  
```  
  
 <span data-ttu-id="2ba84-112">Poiché questo schema definisce lo spazio dei nomi di destinazione, una query XPath (ad esempio "Employee") eseguita sullo schema deve includere lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ba84-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against the schema must include the namespace.</span></span>  
  
 <span data-ttu-id="2ba84-113">Si tratta di un'applicazione Visual Basic [!INCLUDE[msCoName](../../../includes/msconame-md.md)] di esempio che esegue una query XPath (x:Employee) sullo schema XSD precedente.</span><span class="sxs-lookup"><span data-stu-id="2ba84-113">This is a sample [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application that executes an XPath query (x:Employee) against the preceding XSD schema.</span></span> <span data-ttu-id="2ba84-114">Per risolvere il prefisso, l'associazione dello spazio dei nomi viene specificata tramite la proprietà Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2ba84-114">To resolve the prefix, the namespace binding is specified by using the namespaces property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ba84-115">Nel codice è necessario specificare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="2ba84-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="2ba84-116">In questo esempio viene inoltre specificato l'utilizzo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) per il provider di dati che richiede l'installazione di un software client di rete aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="2ba84-116">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="2ba84-117">Per ulteriori informazioni, vedere [requisiti di sistema per SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="2ba84-117">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Private Sub Form_Load()  
    Dim con As New ADODB.Connection  
    Dim cmd As New ADODB.Command  
    Dim stm As New ADODB.Stream  
    con.Open "provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
    Set cmd.ActiveConnection = con  
    stm.Open  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    cmd.Properties("Mapping schema") = "C:\DirectoryPath\con-ex.xml"  
    cmd.Properties("namespaces") = "xmlns:x='urn:myschema:Contacts'"  
    '  Debug.Print "Set Command Dialect to DBGUID_XPATH"  
    cmd.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
    cmd.CommandText = "x:Contact"  
    cmd.Execute , , adExecuteStream   
    stm.Position = 0  
    Debug.Print stm.ReadText(adReadAll)  
End Sub  
```  
  
### <a name="to-test-this-application"></a><span data-ttu-id="2ba84-118">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="2ba84-118">To test this application</span></span>  
  
1.  <span data-ttu-id="2ba84-119">Salvare lo schema XSD di esempio in una cartella.</span><span class="sxs-lookup"><span data-stu-id="2ba84-119">Save the sample XSD schema in a folder.</span></span>  
  
2.  <span data-ttu-id="2ba84-120">Creare un progetto eseguibile di Visual Basic in cui copiare il codice.</span><span class="sxs-lookup"><span data-stu-id="2ba84-120">Create a Visual Basic executable project, and copy the code into it.</span></span> <span data-ttu-id="2ba84-121">Modificare il percorso di directory specificato in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2ba84-121">Change the specified directory path as appropriate.</span></span>  
  
3.  <span data-ttu-id="2ba84-122">Aggiungere il riferimento al progetto seguente:</span><span class="sxs-lookup"><span data-stu-id="2ba84-122">Add the following project reference:</span></span>  
  
    ```  
    "Microsoft ActiveX Data Objects 2.8 Library"  
    ```  
  
4.  <span data-ttu-id="2ba84-123">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2ba84-123">Execute the application.</span></span>  
  
 <span data-ttu-id="2ba84-124">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="2ba84-124">This is the partial result:</span></span>  
  
```  
<y0:Employee xmlns:y0="urn:myschema:Contacts"   
             LName="Achong" CID="1" FName="Gustavo"/>  
<y0:Employee xmlns:y0="urn:myschema:Employees"   
             LName="Abel" CID="2" FName="Catherine"/>  
```  
  
 <span data-ttu-id="2ba84-125">I prefissi generati nel documento XML sono arbitrari, ma consentono di eseguire il mapping allo stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ba84-125">The prefixes that are generated in the XML document are arbitrary, but they map to the same namespace.</span></span>  
  
  
