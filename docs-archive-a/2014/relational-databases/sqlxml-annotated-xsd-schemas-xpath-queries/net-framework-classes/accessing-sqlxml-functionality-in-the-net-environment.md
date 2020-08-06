---
title: Accesso alla funzionalità SQLXML nell'ambiente .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], accessing SQLXML functionality
- SQLXML Managed Classes, accessing SQLXML functionality
- DiffGrams [SQLXML], accessing SQLXML functionality
- .NET Framework [SQLXML], accessing SQLXML functionality
ms.assetid: 74744535-2945-414d-9a5b-7e8cc363953a
author: rothja
ms.author: jroth
ms.openlocfilehash: a2ba0a54310833c0a1a1315aa94d78fe5650d480
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629295"
---
# <a name="accessing-sqlxml-functionality-in-the-net-environment"></a><span data-ttu-id="f4972-102">Accesso alla funzionalità SQLXML nell'ambiente .NET</span><span class="sxs-lookup"><span data-stu-id="f4972-102">Accessing SQLXML Functionality in the .NET Environment</span></span>
  <span data-ttu-id="f4972-103">Questo esempio mostra:</span><span class="sxs-lookup"><span data-stu-id="f4972-103">This example shows:</span></span>  
  
-   <span data-ttu-id="f4972-104">Come utilizzare [!INCLUDE[msCoName](../../../includes/msconame-md.md)] le classi gestite SQLXML (Microsoft. Data. SQLXML) per accedere a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nell' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] ambiente .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f4972-104">How to use [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes (Microsoft.Data.SqlXml) to access Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment.</span></span>  
  
-   <span data-ttu-id="f4972-105">Come i DiffGram generati nell'ambiente .NET Framework possono applicare aggiornamenti dei dati alle tabelle di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4972-105">How DiffGrams that are generated in the .NET Framework environment can apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="f4972-106">In questa applicazione viene eseguita una query XPath su uno schema XSD.</span><span class="sxs-lookup"><span data-stu-id="f4972-106">In this application, an XPath query is executed against an XSD schema.</span></span> <span data-ttu-id="f4972-107">L'esecuzione della query XPath restituisce un documento XML costituito da dati di contatto (**FirstName**, **LastName**).</span><span class="sxs-lookup"><span data-stu-id="f4972-107">The execution of the XPath query returns an XML document that consists of contact data (**FirstName**, **LastName**).</span></span> <span data-ttu-id="f4972-108">L'applicazione carica il documento XML nel set di dati nell'ambiente .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f4972-108">The application loads the XML document in the dataset in the .NET Framework environment.</span></span> <span data-ttu-id="f4972-109">I dati nel set di dati vengono modificati: il nome del contatto viene modificato in "Susan" per il primo contatto nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="f4972-109">The data in the dataset is modified: the contact's first name is changed to "Susan" for the first contact in the dataset.</span></span> <span data-ttu-id="f4972-110">Il DiffGram viene generato dal set di dati e l'aggiornamento specificato nel DiffGram (la modifica nel nome del dipendente) viene quindi applicato alla tabella Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="f4972-110">The DiffGram is generated from the dataset, and the update that is specified in the DiffGram (the change in the employee's first name) is then applied to the Person.Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4972-111">Nel codice è necessario specificare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="f4972-111">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      DataRow row;  
      SqlXmlAdapter ad;  
      //need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandText = "Con";  
      cmd.CommandType = SqlXmlCommandType.XPath;  
      cmd.SchemaPath = "MySchema.xml";  
      //load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      row = ds.Tables["Con"].Rows[0];  
      row["FName"] = "Susan";  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
 <span data-ttu-id="f4972-112">**Per testare l'esempio:**</span><span class="sxs-lookup"><span data-stu-id="f4972-112">**To test the example:**</span></span>  
  
 <span data-ttu-id="f4972-113">Per testare questo esempio, è necessario che nel computer sia installato [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f4972-113">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
1.  <span data-ttu-id="f4972-114">Salvare questo schema XSD (MySchema.xml) in una cartella:</span><span class="sxs-lookup"><span data-stu-id="f4972-114">Save this XSD schema (MySchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Con" sql:relation="Person.Contact" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="FName"    
                         sql:field="FirstName"   
                         type="xsd:string" />   
            <xsd:element name="LName"    
                         sql:field="LastName"    
                         type="xsd:string" />  
         </xsd:sequence>  
         <xsd:attribute name="ContactID" type="xsd:integer" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
2.  <span data-ttu-id="f4972-115">Salvare il codice C# (DocSample.cs) fornito in questo esempio nella stessa cartella nella quale viene archiviato lo schema.</span><span class="sxs-lookup"><span data-stu-id="f4972-115">Save the C# code (DocSample.cs) provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="f4972-116">Se si archiviano i file in un'altra cartella, sarà necessario modificare il codice e specificare il percorso di directory appropriato per lo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="f4972-116">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="f4972-117">Compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="f4972-117">Compile the code.</span></span> <span data-ttu-id="f4972-118">Per compilare il codice al prompt dei comandi, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="f4972-118">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="f4972-119">Viene creato un file eseguibile (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="f4972-119">This creates an executable (DocSample.exe).</span></span>  
  
 <span data-ttu-id="f4972-120">Al prompt dei comandi eseguire DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="f4972-120">At the command prompt, execute DocSample.exe.</span></span>  
  
  
