---
title: Esecuzione di file modello tramite la proprietà CommandText | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- executing template files [SQLXML]
- CommandText property
ms.assetid: f1b1278d-252d-4a06-836e-4ef77f338ef9
author: rothja
ms.author: jroth
ms.openlocfilehash: f5507e84daf57ca4646fae3efe78c6105af35700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623117"
---
# <a name="executing-template-files-by-using-the-commandtext-property"></a><span data-ttu-id="03652-102">Esecuzione di file modello mediante la proprietà CommandText</span><span class="sxs-lookup"><span data-stu-id="03652-102">Executing Template Files by Using the CommandText Property</span></span>
  <span data-ttu-id="03652-103">Questo esempio illustra il modo in cui è possibile specificare i file modello che sono costituiti da query SQL o XPath usando CommandTextproperty.</span><span class="sxs-lookup"><span data-stu-id="03652-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandTextproperty.</span></span> <span data-ttu-id="03652-104">Anziché specificare la query SQL o XPath come valore di CommandText, è possibile specificare un nome di file come valore.</span><span class="sxs-lookup"><span data-stu-id="03652-104">Instead of specifying the SQL or XPath query as the value of CommandText, you can specify a file name as the value.</span></span> <span data-ttu-id="03652-105">Nell'esempio seguente la proprietà CommandType viene specificata come SqlXmlCommandType. TemplateFile.</span><span class="sxs-lookup"><span data-stu-id="03652-105">In the following example, the CommandType property is specified as SqlXmlCommandType.TemplateFile.</span></span>  
  
 <span data-ttu-id="03652-106">L'applicazione di esempio esegue questo modello:</span><span class="sxs-lookup"><span data-stu-id="03652-106">The sample application executes this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="03652-107">Si tratta dell'applicazione C# di esempio.</span><span class="sxs-lookup"><span data-stu-id="03652-107">This is the C# sample application.</span></span> <span data-ttu-id="03652-108">Per testare l'applicazione, salvare il modello (TemplateFile.xml), quindi eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="03652-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03652-109">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="03652-109">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandType = SqlXmlCommandType.TemplateFile;  
         cmd.CommandText = "TemplateFile.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="03652-110">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="03652-110">To test the application</span></span>  
  
1.  <span data-ttu-id="03652-111">Assicurarsi che [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework sia installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="03652-111">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="03652-112">Salvare il modello XML (TemplateFile.xml) fornito in questo esempio in una cartella.</span><span class="sxs-lookup"><span data-stu-id="03652-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="03652-113">Salvare il codice C# (DocSample.cs) fornito in questo esempio nella stessa cartella nella quale viene archiviato lo schema.</span><span class="sxs-lookup"><span data-stu-id="03652-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="03652-114">Se si archiviano i file in un'altra cartella, sarà necessario modificare il codice e specificare il percorso di directory appropriato per lo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="03652-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="03652-115">Compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="03652-115">Compile the code.</span></span> <span data-ttu-id="03652-116">Per compilare il codice al prompt dei comandi, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="03652-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="03652-117">Viene creato un file eseguibile (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="03652-117">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="03652-118">Al prompt dei comandi eseguire DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="03652-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="03652-119">Se si passa un parametro a un modello, il nome del parametro deve iniziare con il simbolo di chiocciola (@); ad esempio, p.Name = " @ContactID ", dove p è un oggetto SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="03652-119">If you pass a parameter to a template, the parameter name must begin with at sign (@); for example, p.Name="@ContactID", where p is a SqlXmlParameter object.</span></span>  
  
 <span data-ttu-id="03652-120">Si tratta del modello aggiornato che accetta solo un parametro.</span><span class="sxs-lookup"><span data-stu-id="03652-120">This is the updated template which takes one parameter.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='ContactID'>1</sql:param>    
  </sql:header>  
  <sql:query>  
    SELECT ContactID, FirstName, LastName  
    FROM   Person.Contact  
    WHERE  ContactID=@ContactID  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="03652-121">Si tratta del codice aggiornato nel quale un parametro viene passato per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="03652-121">This is the updated code in which a parameter is passed in to execute the template.</span></span>  
  
```  
public static int testParams()  
{  
  
   Stream strm;  
   SqlXmlParameter p;  
  
   SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
   cmd.CommandType = SqlXmlCommandType.TemplateFile;  
   cmd.CommandText = "TemplateFile.xml";  
   p = cmd.CreateParameter();  
   p.Name="@ContactID";  
   p.Value = "1";  
   strm = cmd.ExecuteStream();  
   StreamReader sw = new StreamReader(strm);  
   Console.WriteLine(sw.ReadToEnd());  
   return 0;        
}  
```  
  
  
