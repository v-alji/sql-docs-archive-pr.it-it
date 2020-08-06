---
title: Esecuzione di query XPath con spazi dei nomi (classi gestite SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces property
- XPath queries [SQLXML], SQLXML Managed Classes
- queries [SQLXML], SQLXML Managed Classes
- XPath queries [SQLXML], namespaces
- Managed Classes [SQLXML], executing XPath queries
- SQLXML Managed Classes, executing XPath queries
- namespaces [SQLXML], XPath queries
ms.assetid: c6fc46d8-6b42-4992-a8f1-a8d4b8886e6e
author: rothja
ms.author: jroth
ms.openlocfilehash: a2d726de95929709c1ae958ee22388df3195bc84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623115"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxml-managed-classes"></a><span data-ttu-id="7f462-102">Esecuzione di query XPath con spazi dei nomi (classi gestite SQLXML)</span><span class="sxs-lookup"><span data-stu-id="7f462-102">Executing XPath Queries with Namespaces (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="7f462-103">Le query XPath possono includere spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7f462-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="7f462-104">Se gli elementi dello schema sono qualificati con spazio dei nomi, ovvero utilizzano uno spazio dei nomi di destinazione, le query XPath sullo schema devono specificare lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7f462-104">If the schema elements are namespace-qualified (use a target namespace), the XPath queries against the schema must specify the namespace.</span></span>  
  
 <span data-ttu-id="7f462-105">Poiché l'utilizzo del carattere jolly (\*) non è supportato in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, è necessario specificare la query XPath utilizzando un prefisso di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7f462-105">Because the wildcard character (\*) is not supported in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="7f462-106">Per risolvere il prefisso, utilizzare la proprietà Namespaces per specificare l'associazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7f462-106">To resolve the prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="7f462-107">Nell'esempio seguente, la query XPath specifica gli spazi dei nomi usando il carattere jolly ( \* ) e le funzioni XPath local-name () e Namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="7f462-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="7f462-108">La query XPath restituisce tutti gli elementi in cui il nome locale è `Employee` e l'URI dello spazio dei nomi è `urn:myschema:Contacts`.</span><span class="sxs-lookup"><span data-stu-id="7f462-108">This XPath query returns all the elements where the local name is `Employee` and the namespace URI is `urn:myschema:Contacts`:</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="7f462-109">In SQLXML 4.0 specificare questa query XPath con un prefisso di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7f462-109">In SQLXML 4.0, specify this XPath query with a namespace prefix.</span></span> <span data-ttu-id="7f462-110">Un esempio è costituito da `x:Contact`, dove `x` è il prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7f462-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="7f462-111">Si consideri lo schema XSD seguente:</span><span class="sxs-lookup"><span data-stu-id="7f462-111">Consider the following XSD schema:</span></span>  
  
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
  
 <span data-ttu-id="7f462-112">Poiché questo schema definisce lo spazio dei nomi di destinazione, una query XPath, ad esempio "Employee", eseguita sullo schema deve includere lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7f462-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against this schema must include the namespace.</span></span>  
  
 <span data-ttu-id="7f462-113">Nell'applicazione di esempio C# seguente viene eseguita una query XPath sullo schema XSD precedente (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="7f462-113">The following C# sample application executes an XPath query against the preceding XSD schema (MySchema.xml).</span></span> <span data-ttu-id="7f462-114">Per risolvere il prefisso, specificare l'associazione dello spazio dei nomi utilizzando la proprietà Namespaces dell'oggetto SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="7f462-114">To resolve the prefix, specify the namespace binding by using the Namespaces property of the SqlXmlCommand object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f462-115">Nel codice è necessario specificare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="7f462-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXPath()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "x:Contact[@CID='1']";  
         cmd.CommandType = SqlXmlCommandType.XPath;  
         cmd.RootTag = "ROOT";  
         cmd.Namespaces = "xmlns:x='urn:myschema:Contacts'";  
         cmd.SchemaPath = "MySchema.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXPath();  
         return 0;  
      }  
   }  
```  
  
 <span data-ttu-id="7f462-116">Per testare questo esempio, è necessario che nel computer sia installato [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f462-116">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="7f462-117">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="7f462-117">To test the application</span></span>  
  
1.  <span data-ttu-id="7f462-118">Salvare lo schema XSD (MySchema.xml) fornito in questo esempio in una cartella.</span><span class="sxs-lookup"><span data-stu-id="7f462-118">Save the XSD schema (MySchema.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="7f462-119">Salvare il codice C# (DocSample.cs) fornito in questo esempio nella stessa cartella nella quale viene archiviato lo schema.</span><span class="sxs-lookup"><span data-stu-id="7f462-119">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="7f462-120">Se si archiviano i file in un'altra cartella, sarà necessario modificare il codice e specificare il percorso di directory appropriato per lo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="7f462-120">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="7f462-121">Compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="7f462-121">Compile the code.</span></span> <span data-ttu-id="7f462-122">Per compilare il codice al prompt dei comandi, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="7f462-122">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="7f462-123">Viene creato un file eseguibile (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="7f462-123">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="7f462-124">Al prompt dei comandi eseguire DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="7f462-124">At the command prompt, execute DocSample.exe.</span></span>  
  
  
