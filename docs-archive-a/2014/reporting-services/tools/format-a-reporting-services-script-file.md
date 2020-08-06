---
title: Formattare un file script di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], formats
- formats [Reporting Services], script files
ms.assetid: 85a207dd-4e0f-4d40-a41e-0c75f65d719c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c98a2f6561c3242fec34f7ca11c8304286ccebae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716039"
---
# <a name="format-a-reporting-services-script-file"></a><span data-ttu-id="d7327-102">Formattare un file script di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d7327-102">Format a Reporting Services Script File</span></span>
  <span data-ttu-id="d7327-103">Uno script [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è un file di codice [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET, specificato su un proxy compilato in WSDL (Web Service Description Language), che definisce l'API SOAP di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d7327-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET code file, written against a proxy that is built on Web Service Description Language (WSDL), which defines the Reporting Services SOAP API.</span></span> <span data-ttu-id="d7327-104">Un file script viene archiviato come file di testo Unicode o UTF-8 con estensione .rss.</span><span class="sxs-lookup"><span data-stu-id="d7327-104">A script file is stored as a Unicode or UTF-8 text file with the extension .rss.</span></span>  
  
 <span data-ttu-id="d7327-105">Il file script funge da modulo [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] e può contenere procedure definite dall'utente e variabili a livello del modulo.</span><span class="sxs-lookup"><span data-stu-id="d7327-105">The script file acts as a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] module and can contain user-defined procedures and module-level variables.</span></span> <span data-ttu-id="d7327-106">Per una corretta esecuzione, il file script deve contenere una routine Main.</span><span class="sxs-lookup"><span data-stu-id="d7327-106">For the script file to run successfully, it must contain a Main procedure.</span></span> <span data-ttu-id="d7327-107">La routine Main è la prima routine alla quale viene eseguito l'accesso quando si esegue il file script.</span><span class="sxs-lookup"><span data-stu-id="d7327-107">The Main procedure is the first procedure that is accessed when your script file runs.</span></span> <span data-ttu-id="d7327-108">Nella routine Main è possibile aggiungere le operazioni del servizio Web ed eseguire le sottoroutine definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d7327-108">Main is where you can add your Web service operations and run your user defined subprocedures.</span></span> <span data-ttu-id="d7327-109">Nel codice seguente viene creata una routine Main:</span><span class="sxs-lookup"><span data-stu-id="d7327-109">The following code creates a Main procedure:</span></span>  
  
```  
Public Sub Main()  
    ' Your code goes here.  
End Sub  
```  
  
 <span data-ttu-id="d7327-110">L'ambiente di script si connette automaticamente al server di report, crea la classe proxy Web e genera una variabile di riferimento (*rs*) nell'oggetto proxy del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="d7327-110">The script environment automatically connects to the report server, creates the Web proxy class, and generates a reference variable (*rs*) to the Web service proxy object.</span></span> <span data-ttu-id="d7327-111">Le singole istruzioni che vengono create devono solo fare riferimento alla variabile a livello di modulo *rs* per eseguire una delle operazioni del servizio Web disponibili nella libreria del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="d7327-111">Individual statements that you create need only refer to the *rs* module-level variable to perform any of the Web service operations that are available in the Web service library.</span></span> <span data-ttu-id="d7327-112">Il codice [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] seguente chiama il metodo <xref:ReportService2010.ReportingService2010.ListChildren%2A> del servizio Web dall'interno di un file script:</span><span class="sxs-lookup"><span data-stu-id="d7327-112">The following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code calls the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method from within a script file:</span></span>  
  
```  
Public Sub Main()  
    Dim items() As CatalogItem  
    items = rs.ListChildren("/", True)  
  
    Dim item As CatalogItem  
    For Each item In items  
        Console.WriteLine(item.Name)  
    Next item  
End Sub   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7327-113">Le credenziali dell'utente vengono gestite dall'ambiente di script e vengono passate agli argomenti del prompt dei comandi tramite RS.exe.</span><span class="sxs-lookup"><span data-stu-id="d7327-113">User credentials are managed by the script environment and passed through command prompt arguments through the use of RS.exe.</span></span> <span data-ttu-id="d7327-114">Anche se è possibile usare la variabile *rs* per impostare l'autenticazione del servizio Web, si consiglia di usare l'ambiente di script.</span><span class="sxs-lookup"><span data-stu-id="d7327-114">Although you can use the *rs* variable to set the authentication of the Web service, it is recommended that you use the script environment.</span></span> <span data-ttu-id="d7327-115">Non è necessario autenticare il servizio Web nel file script.</span><span class="sxs-lookup"><span data-stu-id="d7327-115">You do not need to authenticate the Web service in the script file itself.</span></span> <span data-ttu-id="d7327-116">Per altre informazioni sull'autenticazione degli ambienti di script, vedere [Utilità RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d7327-116">For more information about authenticating the script environment, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span>  
  
 <span data-ttu-id="d7327-117">Non dichiarare gli spazi dei nomi all'interno del file script.</span><span class="sxs-lookup"><span data-stu-id="d7327-117">You do not declare namespaces within the script file.</span></span> <span data-ttu-id="d7327-118">L'ambiente di scripting rende disponibili diversi utili spazi dei nomi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml** e **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="d7327-118">The scripting environment makes several useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces available to you: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml**, and **System.IO**.</span></span>  
  
 <span data-ttu-id="d7327-119">Per esempi di script, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889)(Esempi del prodotto SQL Server Reporting Services).</span><span class="sxs-lookup"><span data-stu-id="d7327-119">For script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7327-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7327-120">See Also</span></span>  
 <span data-ttu-id="d7327-121">[Servizio Web ReportServer](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="d7327-121">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="d7327-122">[Riferimento tecnico &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d7327-122">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="d7327-123">Utilità RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d7327-123">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
