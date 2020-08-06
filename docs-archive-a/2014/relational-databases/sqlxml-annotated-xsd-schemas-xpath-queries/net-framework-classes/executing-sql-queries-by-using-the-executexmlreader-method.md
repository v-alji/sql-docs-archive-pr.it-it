---
title: Esecuzione di query SQL tramite il metodo ExecuteXMLReader | Microsoft Docs
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
- ExecuteXmlReader method
- SQL queries [SQLXML]
ms.assetid: f106a4c5-8d6e-40c0-bf1f-11e121afcb01
author: rothja
ms.author: jroth
ms.openlocfilehash: 1570e877ae84a813e5a053df34c35d5fe840969c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629279"
---
# <a name="executing-sql-queries-by-using-the-executexmlreader-method"></a><span data-ttu-id="68dc5-102">Esecuzione di query SQL tramite il metodo ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="68dc5-102">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>
  <span data-ttu-id="68dc5-103">Anziché usare il metodo ExecuteToStream, è possibile usare il metodo ExecuteXmlReader dell'oggetto SqlXmlCommand per eseguire i comandi.</span><span class="sxs-lookup"><span data-stu-id="68dc5-103">Instead of using the ExecuteToStream method, you can use the ExecuteXmlReader method of the SqlXmlCommand object to execute commands.</span></span> <span data-ttu-id="68dc5-104">Questo metodo restituisce un oggetto XmlReader che può essere utilizzato per un'ulteriore elaborazione del risultato (in questo esempio vengono stampati i nomi degli elementi o degli attributi e i valori).</span><span class="sxs-lookup"><span data-stu-id="68dc5-104">This method returns an XmlReader object that can be used for further processing of the result (which in this example is printing the element or attribute names and the values).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68dc5-105">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="68dc5-105">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
using System.Xml;  
   class Test  
   {  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks2012;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         SqlXmlParameter p;  
         XmlReader Reader;  
         XmlTextWriter tw;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "select FirstName, LastName from Person.Person where LastName = ? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         Reader = cmd.ExecuteXmlReader();  
            tw = new XmlTextWriter(Console.Out);  
         Reader.MoveToContent();  
         tw.WriteNode(Reader, false);  
         tw.Flush();  
         tw.Close();  
         Reader.Close();  
  
         return 0;  
      }  
  
      static int Main(string[] args)  
      {  
         testParams();  
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="68dc5-106">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="68dc5-106">To test the application</span></span>  
  
1.  <span data-ttu-id="68dc5-107">Assicurarsi che [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework sia installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="68dc5-107">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="68dc5-108">Salvare in una cartella il codice C# (DocSample.cs) fornito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="68dc5-108">Save the C# code (DocSample.cs) that is provided in this topic in a folder.</span></span>  
  
3.  <span data-ttu-id="68dc5-109">Compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="68dc5-109">Compile the code.</span></span> <span data-ttu-id="68dc5-110">Per compilare il codice al prompt dei comandi, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="68dc5-110">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="68dc5-111">Viene creato un file eseguibile (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="68dc5-111">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="68dc5-112">Al prompt dei comandi eseguire DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="68dc5-112">At the command prompt, execute DocSample.exe.</span></span>  
  
  
