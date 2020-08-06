---
title: Elaborazione di XML sul lato client (classi gestite SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- processing XML on client side [SQLXML]
- client-side XML formatting
- Managed Classes [SQLXML], client-side XML formatting
- SQLXML Managed Classes, client-side XML formatting
- ClientSideXml property
ms.assetid: 5e7ecf18-66fc-49ff-bc50-83635cd7ac0b
author: rothja
ms.author: jroth
ms.openlocfilehash: fb90f7c5c823c750b64f47d0c9df9551b9f857b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624007"
---
# <a name="processing-xml-on-the-client-side-sqlxml-managed-classes"></a><span data-ttu-id="8b863-102">Elaborazione di XML sul lato client (classi gestite SQLXML)</span><span class="sxs-lookup"><span data-stu-id="8b863-102">Processing XML on the Client Side (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="8b863-103">Questo esempio illustra l'uso della proprietà ClientSideXml.</span><span class="sxs-lookup"><span data-stu-id="8b863-103">This example illustrates the use of the ClientSideXml property.</span></span> <span data-ttu-id="8b863-104">L'applicazione esegue una stored procedure nel server.</span><span class="sxs-lookup"><span data-stu-id="8b863-104">The application executes a stored procedure on the server.</span></span> <span data-ttu-id="8b863-105">Il risultato della stored procedure, ovvero un set di righe a due colonne, viene elaborato sul lato client per produrre un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8b863-105">The result of the stored procedure (a two-column rowset) is processed on the client side to produce an XML document.</span></span>  
  
 <span data-ttu-id="8b863-106">Il stored procedure GetContacts seguente restituisce **FirstName** e **LastName** dei dipendenti nella tabella Person. Contact del database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8b863-106">The following GetContacts stored procedure returns **FirstName** and **LastName** of employees in the Person.Contact table in the AdventureWorks database.</span></span>  
  
```  
USE AdventureWorks  
CREATE PROCEDURE GetContacts @LastName varchar(20)  
AS  
SELECT FirstName, LastName  
FROM   Person.Contact  
WHERE LastName = @LastName  
Go  
```  
  
 <span data-ttu-id="8b863-107">Questa applicazione C# esegue il stored procedure e specifica l'opzione FOR XML AUTO in specificando il valore CommandText.</span><span class="sxs-lookup"><span data-stu-id="8b863-107">This C# application executes the stored procedure and specifies the FOR XML AUTO option in specifying the CommandText value.</span></span> <span data-ttu-id="8b863-108">Nell'applicazione, la proprietà ClientSideXml dell'oggetto SqlXmlCommand è impostata su true.</span><span class="sxs-lookup"><span data-stu-id="8b863-108">In the application, the ClientSideXml property of the SqlXmlCommand object is set to true.</span></span> <span data-ttu-id="8b863-109">In questo modo è possibile eseguire stored procedure preesistenti che restituiscono un set di righe e applicano a questo una trasformazione XML sul client.</span><span class="sxs-lookup"><span data-stu-id="8b863-109">This allows you to execute preexisting stored procedures that return a rowset and apply an XML transformation to it on the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b863-110">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="8b863-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.ClientSideXml = true;  
         cmd.CommandText = "EXEC GetContacts ? FOR XML NESTED";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         using (Stream strm = cmd.ExecuteStream())   
         {  
            using (StreamReader sr = new StreamReader(strm))  
                  {  
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
  
 <span data-ttu-id="8b863-111">Per testare questo esempio, è necessario che nel computer sia installato [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b863-111">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="8b863-112">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="8b863-112">To test the application</span></span>  
  
1.  <span data-ttu-id="8b863-113">Creare la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8b863-113">Create the stored procedure.</span></span>  
  
2.  <span data-ttu-id="8b863-114">Salvare in una cartella il codice C# (DocSample.cs) fornito in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8b863-114">Save the C# code (DocSample.cs) that is provided in this example in a folder.</span></span> <span data-ttu-id="8b863-115">Modificare il codice per specificare informazioni di accesso e sulla password appropriate.</span><span class="sxs-lookup"><span data-stu-id="8b863-115">Edit the code to specify appropriate login and password information.</span></span>  
  
3.  <span data-ttu-id="8b863-116">Compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="8b863-116">Compile the code.</span></span> <span data-ttu-id="8b863-117">Per compilare il codice al prompt dei comandi, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="8b863-117">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="8b863-118">Viene creato un file eseguibile (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="8b863-118">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="8b863-119">Al prompt dei comandi eseguire DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="8b863-119">At the command prompt, execute DocSample.exe.</span></span>  
  
  
