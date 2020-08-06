---
title: Esecuzione di file modello tramite la proprietà CommandStream | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- CommandStream property
ms.assetid: 55c564e3-56d1-4d85-bcaa-703e2905dd57
author: rothja
ms.author: jroth
ms.openlocfilehash: c57a2ab2f3780a8bc75b53b0cceeee0799fcfcc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623118"
---
# <a name="executing-template-files-by-using-the-commandstream-property"></a><span data-ttu-id="2375d-102">Esecuzione di file modello tramite la proprietà CommandStream</span><span class="sxs-lookup"><span data-stu-id="2375d-102">Executing Template Files by Using the CommandStream Property</span></span>
  <span data-ttu-id="2375d-103">Questo esempio illustra il modo in cui è possibile specificare i file modello costituiti da query SQL o XPath usando la proprietà CommandStream dell'oggetto SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="2375d-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandStream property of the SqlXmlCommand object.</span></span> <span data-ttu-id="2375d-104">In questa applicazione viene aperto un FileStreamobject per un file di comando e il flusso di file viene assegnato come CommandStream eseguito.</span><span class="sxs-lookup"><span data-stu-id="2375d-104">In this application, a FileStreamobject is opened for a command file, and the file stream is assigned as the CommandStream that is executed.</span></span>  
  
 <span data-ttu-id="2375d-105">Nell'esempio seguente la proprietà CommandType viene specificata come SqlXmlCommandType. template (non come TemplateFile).</span><span class="sxs-lookup"><span data-stu-id="2375d-105">In the following example, the CommandType property is specified as SqlXmlCommandType.Template (not as TemplateFile).</span></span>  
  
 <span data-ttu-id="2375d-106">Di seguito è riportato il modello XML di esempio:</span><span class="sxs-lookup"><span data-stu-id="2375d-106">This is the sample XML template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="2375d-107">Si tratta dell'applicazione C# di esempio.</span><span class="sxs-lookup"><span data-stu-id="2375d-107">This is the sample C# application.</span></span> <span data-ttu-id="2375d-108">Per testare l'applicazione, salvare il modello (TemplateFile.xml), quindi eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2375d-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span> <span data-ttu-id="2375d-109">Nell'applicazione viene eseguita la query specificata nel modello XML e il documento XML generato viene visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="2375d-109">The application executes the query that is specified in the XML template and displays the XML document that is generated on the screen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2375d-110">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="2375d-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         //Stream strm;  
         MemoryStream ms = new MemoryStream();  
         StreamWriter sw = new StreamWriter(ms);  
         ms.Position = 0;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandStream = new FileStream("TemplateFile.xml", FileMode.Open, FileAccess.Read);  
         cmd.CommandType = SqlXmlCommandType.Template;  
         using (Stream strm = cmd.ExecuteStream())  
         {  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;        
      }  
  
      public static int Main(String[] args)  
      {  
         testParams();     
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="2375d-111">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="2375d-111">To test the application</span></span>  
  
1.  <span data-ttu-id="2375d-112">Salvare il modello XML (TemplateFile.xml) fornito in questo esempio in una cartella.</span><span class="sxs-lookup"><span data-stu-id="2375d-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="2375d-113">Salvare il codice C# (DocSample.cs) fornito in questo esempio nella stessa cartella nella quale viene archiviato lo schema.</span><span class="sxs-lookup"><span data-stu-id="2375d-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="2375d-114">Se si archiviano i file in un'altra cartella, sarà necessario modificare il codice e specificare il percorso di directory appropriato per lo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="2375d-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="2375d-115">Compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="2375d-115">Compile the code.</span></span> <span data-ttu-id="2375d-116">Per compilare il codice al prompt dei comandi, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="2375d-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="2375d-117">Viene creato un file eseguibile (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="2375d-117">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="2375d-118">Al prompt dei comandi eseguire DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="2375d-118">At the command prompt, execute DocSample.exe.</span></span>  
  
  
