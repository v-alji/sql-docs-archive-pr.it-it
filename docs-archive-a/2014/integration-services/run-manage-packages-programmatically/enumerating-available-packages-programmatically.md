---
title: Enumerazione dei pacchetti disponibili a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically enumerate packages [SSIS]
- existence testing [Integration Services]
- enumerating packages [Integration Services]
ms.assetid: 254ec7ee-d3ff-4361-8995-46e9b9c4dc95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053f2e598b1cc18e68ee2182092188367ee7f10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713236"
---
# <a name="enumerating-available-packages-programmatically"></a><span data-ttu-id="2595b-102">Enumerazione dei pacchetti disponibili a livello di codice</span><span class="sxs-lookup"><span data-stu-id="2595b-102">Enumerating Available Packages Programmatically</span></span>
  <span data-ttu-id="2595b-103">Quando si utilizzano i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a livello di codice, può essere necessario determinare se esiste un singolo pacchetto o cartella o enumerare i pacchetti salvati disponibili per il caricamento e l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2595b-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to enumerate the saved packages that are available to load and execute.</span></span> <span data-ttu-id="2595b-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> dello spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> fornisce un'ampia varietà di metodi e classi per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="2595b-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="2595b-105">Verifica dell'esistenza di un pacchetto o di una cartella</span><span class="sxs-lookup"><span data-stu-id="2595b-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="2595b-106">Per determinare a livello di codice se un pacchetto salvato esiste, chiamare uno dei metodi seguenti prima di tentare di caricarlo ed eseguirlo:</span><span class="sxs-lookup"><span data-stu-id="2595b-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run it:</span></span>  
  
|<span data-ttu-id="2595b-107">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="2595b-107">Storage Location</span></span>|<span data-ttu-id="2595b-108">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="2595b-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="2595b-109">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="2595b-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="2595b-110">Per determinare a livello di codice se una cartella esiste prima di tentare di elencare i pacchetti archiviati al suo interno, chiamare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2595b-110">To determine programmatically whether a folder exists before attempting to list the packages stored in it, call one of the following methods:</span></span>  
  
|<span data-ttu-id="2595b-111">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="2595b-111">Storage Location</span></span>|<span data-ttu-id="2595b-112">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="2595b-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="2595b-113">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="2595b-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  
 [<span data-ttu-id="2595b-114">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2595b-114">Back to top</span></span>](#top)  
  
##  <a name="enumerating-available-packages"></a><a name="listing"></a> <span data-ttu-id="2595b-115">Enumerazione dei pacchetti disponibili</span><span class="sxs-lookup"><span data-stu-id="2595b-115">Enumerating Available Packages</span></span>  
 <span data-ttu-id="2595b-116">Per ottenere a livello di codice un elenco dei pacchetti salvati, chiamare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2595b-116">To obtain a list of saved packages programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="2595b-117">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="2595b-117">Storage Location</span></span>|<span data-ttu-id="2595b-118">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="2595b-118">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="2595b-119">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="2595b-119">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>|  
  
 <span data-ttu-id="2595b-120">Gli esempi seguenti sono applicazioni console che dimostrano l'utilizzo di questi metodi.</span><span class="sxs-lookup"><span data-stu-id="2595b-120">The following samples are console applications that demonstrate the use of these methods.</span></span>  
  
###  <a name="example-ssis-package-store"></a><a name="listing_store"></a> <span data-ttu-id="2595b-121">Esempio (archivio pacchetti SSIS)</span><span class="sxs-lookup"><span data-stu-id="2595b-121">Example (SSIS Package Store)</span></span>  
 <span data-ttu-id="2595b-122">Utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> per elencare i pacchetti archiviati nell'archivio pacchetti SSIS.</span><span class="sxs-lookup"><span data-stu-id="2595b-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> method to list packages stored in the SSIS Package Store.</span></span> <span data-ttu-id="2595b-123">I percorsi di archiviazione predefiniti gestiti dall'archivio pacchetti SSIS sono File system e MSDB.</span><span class="sxs-lookup"><span data-stu-id="2595b-123">The default storage locations that are managed by the SSIS Package store are File System and MSDB.</span></span> <span data-ttu-id="2595b-124">In questi percorsi è possibile creare altre cartelle logiche.</span><span class="sxs-lookup"><span data-stu-id="2595b-124">You can create additional logical folders within these locations.</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlServer = "."  
  
    ssisApplication = New Application()  
  
    ' Get packages stored in MSDB.  
    sqlFolder = "MSDB"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in MSDB:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
      Console.WriteLine()  
    End If  
  
    ' Get packages stored in the File System.  
    sqlFolder = "File System"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in the File System:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
    End If  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSSIS_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlServer = ".";  
  
      ssisApplication = new Application();  
  
      // Get packages stored in MSDB.  
      sqlFolder = "MSDB";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in MSDB:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
        Console.WriteLine();  
      }  
  
      // Get packages stored in the File System.  
      sqlFolder = "File System";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in the File System:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
      }  
  
      Console.Read();  
  
    }  
  
  }  
  
}  
```  
  
 [<span data-ttu-id="2595b-125">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2595b-125">Back to top</span></span>](#top)  
  
###  <a name="example-sql-server"></a><a name="listing_sql"></a> <span data-ttu-id="2595b-126">Esempio (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2595b-126">Example (SQL Server)</span></span>  
 <span data-ttu-id="2595b-127">Utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> per elencare i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] archiviati in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2595b-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> method to list [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that are stored in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
    Dim sqlUser As String  
    Dim sqlPassword As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlFolder = String.Empty  
    sqlServer = "(local)"  
    sqlUser = String.Empty  
    sqlPassword = String.Empty  
  
    ssisApplication = New Application()  
  
    sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword)  
  
    For Each sqlPackage In sqlPackages  
      Console.WriteLine(sqlPackage.Name)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSql_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
      string sqlUser;  
      string sqlPassword;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlFolder = String.Empty;  
      sqlServer = "(local)";  
      sqlUser = String.Empty;  
      sqlPassword = String.Empty;  
  
      ssisApplication = new Application();  
  
      sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword);  
  
      foreach (PackageInfo sqlPackage in sqlPackages)  
      {  
        Console.WriteLine(sqlPackage.Name);  
      }  
  
      Console.Read();  
  
    }  
  }  
}  
```  
  
 [<span data-ttu-id="2595b-128">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2595b-128">Back to top</span></span>](#top)  
  
<span data-ttu-id="2595b-129">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2595b-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2595b-130">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="2595b-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2595b-131">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="2595b-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2595b-132">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2595b-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2595b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2595b-133">See Also</span></span>  
 [<span data-ttu-id="2595b-134">Gestione dei pacchetti &#40;servizio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2595b-134">Package Management &#40;SSIS Service&#41;</span></span>](../service/package-management-ssis-service.md)  
  
  
