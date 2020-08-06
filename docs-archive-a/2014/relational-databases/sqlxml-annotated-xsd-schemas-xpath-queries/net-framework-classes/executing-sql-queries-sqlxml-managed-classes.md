---
title: Esecuzione di query SQL (classi gestite SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXML Managed Classes
- SQLXML Managed Classes, executing SQL queries
- Managed Classes [SQLXML], executing SQL queries
- ExecuteToStream method
- SQL queries [SQLXML]
ms.assetid: a561ae83-a8b6-4b9b-a819-9b86839546b4
author: rothja
ms.author: jroth
ms.openlocfilehash: d869e45de359e602b2451b9f66fa3046f6823c1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629277"
---
# <a name="executing-sql-queries-sqlxml-managed-classes"></a><span data-ttu-id="3cf3f-102">Esecuzione di query SQL (classi gestite SQLXML)</span><span class="sxs-lookup"><span data-stu-id="3cf3f-102">Executing SQL Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="3cf3f-103">In questo esempio vengono illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cf3f-103">This example demonstrates:</span></span>  
  
-   <span data-ttu-id="3cf3f-104">Creazione di parametri (oggetti SqlXmlParameter).</span><span class="sxs-lookup"><span data-stu-id="3cf3f-104">Creating parameters (SqlXmlParameter objects).</span></span>  
  
-   <span data-ttu-id="3cf3f-105">Assegnazione di valori alle proprietà (nome e valore) degli oggetti SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-105">Assigning values to the properties (Name and Value) of SqlXmlParameter objects.</span></span>  
  
 <span data-ttu-id="3cf3f-106">In questo esempio viene eseguita una query SQL semplice per recuperare il nome, il cognome e la data di nascita del dipendente il cui valore di cognome viene passato come parametro.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-106">In this example, a simple SQL query is executed to retrieve the first name, last name, and birth date of the employee whose last name value is passed as a parameter.</span></span> <span data-ttu-id="3cf3f-107">Quando si specifica il parametro (*LastName*), viene impostata solo la proprietà Value.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-107">In specifying the parameter (*LastName*), only the Value property is set.</span></span> <span data-ttu-id="3cf3f-108">La proprietà Name non è impostata perché in questa query il parametro è posizionale e non è necessario alcun nome.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-108">The Name property is not set, because in this query the parameter is positional and no name is required.</span></span>  
  
 <span data-ttu-id="3cf3f-109">Per impostazione predefinita, la proprietà CommandType dell'oggetto SqlXmlCommand è **SQL**.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-109">The CommandType property of the SqlXmlCommand object by default is **Sql**.</span></span> <span data-ttu-id="3cf3f-110">La proprietà, pertanto, non viene impostata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-110">Therefore, the property is not explicitly set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3cf3f-111">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
 <span data-ttu-id="3cf3f-112">Di seguito viene fornito il codice C#:</span><span class="sxs-lookup"><span data-stu-id="3cf3f-112">This is the C# code:</span></span>  
  
```  
using System;  
  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);        
         cmd.CommandText = "SELECT FirstName, LastName FROM Person.Contact WHERE LastName=? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         string strResult;  
         try   
         {  
            strm = cmd.ExecuteStream();  
            strm.Position = 0;  
            using(StreamReader sr = new StreamReader(strm))  
            {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         catch (SqlXmlException e)  
         {  
            //in case of an error, this prints error returned.  
            e.ErrorStream.Position=0;  
            strResult=new StreamReader(e.ErrorStream).ReadToEnd();  
            System.Console.WriteLine(strResult);  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="3cf3f-113">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="3cf3f-113">To test the application</span></span>  
  
1.  <span data-ttu-id="3cf3f-114">Salvare in una cartella il codice C# (DocSample.cs) fornito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-114">Save the C# code (DocSample.cs) provided in this topic in a folder.</span></span>  
  
2.  <span data-ttu-id="3cf3f-115">Compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-115">Compile the code.</span></span> <span data-ttu-id="3cf3f-116">Per compilare il codice al prompt dei comandi, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="3cf3f-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="3cf3f-117">Viene creato un file eseguibile (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="3cf3f-117">This creates an executable (DocSample.exe).</span></span>  
  
3.  <span data-ttu-id="3cf3f-118">Al prompt dei comandi eseguire DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="3cf3f-119">Per testare questo esempio, è necessario che nel computer sia installato [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-119">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
 <span data-ttu-id="3cf3f-120">Anziché specificare query SQL come testo del comando, è possibile specificare un modello, come illustrato nel frammento di codice seguente, che esegua un updategram (che è anche un modello) per inserire un record del consumer.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-120">Instead of specifying SQL queries as the command text, you can specify a template (as shown in the following code fragment) that executes an updategram (which is also a template) to insert a customer record.</span></span> <span data-ttu-id="3cf3f-121">È possibile specificare modelli e updategram in file e file di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-121">You can specify templates and updategrams in files and execute files.</span></span> <span data-ttu-id="3cf3f-122">Per ulteriori informazioni, vedere [esecuzione di file modello tramite la proprietà CommandText](executing-template-files-by-using-the-commandtext-property.md).</span><span class="sxs-lookup"><span data-stu-id="3cf3f-122">For more information, see [Executing Template Files by Using the CommandText Property](executing-template-files-by-using-the-commandtext-property.md).</span></span>  
  
```  
SqlXmlCommand cmd = new SqlXmlCommand("Provider=SQLOLEDB;Data Source=SqlServerName;Initial Catalog=Database; Integrated Security=SSPI;");  
Stream stm;  
cmd.CommandType = SqlXmlCommandType.UpdateGram;  
cmd.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' xmlns:updg='urn:schemas-microsoft-com:xml-updategram'>" +  
      "<updg:sync>" +  
       "<updg:before/>" +  
       "<updg:after>" +  
         "<Customer CustomerID='aaaaa' CustomerName='Some Name' CustomerTitle='SomeTitle' />" +  
       "</updg:after>" +  
       "</updg:sync>" +  
       "</ROOT>";  
  
stm = cmd.ExecuteStream();  
stm = null;  
cmd = null;  
```  
  
## <a name="using-executetostream"></a><span data-ttu-id="3cf3f-123">Utilizzo di ExecuteToStream</span><span class="sxs-lookup"><span data-stu-id="3cf3f-123">Using ExecuteToStream</span></span>  
 <span data-ttu-id="3cf3f-124">Se si dispone di un flusso esistente, è possibile usare il metodo ExecuteToStream anziché creare un oggetto flusso e usare il metodo Execute.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-124">If you have an existing stream, you can use the ExecuteToStream method instead of creating a Stream object and using the Execute method.</span></span> <span data-ttu-id="3cf3f-125">Il codice dell'esempio precedente è stato modificato qui per usare il metodo ExecuteToStream:</span><span class="sxs-lookup"><span data-stu-id="3cf3f-125">The code from the preceding example is revised here to use the ExecuteToStream method:</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlParameter p;  
      MemoryStream ms = new MemoryStream();  
      StreamReader sr = new StreamReader(ms);  
      ms.Position = 0;  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.CommandText = "select FirstName, LastName from Person.Contact where LastName = ? For XML Auto";  
      p = cmd.CreateParameter();  
      p.Value = "Achong";  
      cmd.ExecuteToStream(ms);  
      ms.Position = 0;  
      Console.WriteLine(sr.ReadToEnd());  
      return 0;        
   }  
   public static int Main(String[] args)  
   {  
      testParams();     
      return 0;  
   }  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3cf3f-126">È anche possibile usare ExecuteXMLReadermethod che restituisce un oggetto XmlReader.</span><span class="sxs-lookup"><span data-stu-id="3cf3f-126">You can also use the ExecuteXMLReadermethod that returns an XmlReader object.</span></span> <span data-ttu-id="3cf3f-127">Per ulteriori informazioni, vedere [esecuzione di query SQL tramite il metodo ExecuteXmlReader](executing-sql-queries-by-using-the-executexmlreader-method.md).</span><span class="sxs-lookup"><span data-stu-id="3cf3f-127">For more information, see [Executing SQL Queries by Using the ExecuteXMLReader Method](executing-sql-queries-by-using-the-executexmlreader-method.md).</span></span>  
  
  
