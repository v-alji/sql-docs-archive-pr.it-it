---
title: Impostazione della proprietà Url del servizio Web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Url property
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: 4eac4e40-dafb-4403-acde-13df317c8ec8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 08178ae66a7bb53d6f155e7410bbc7436e048212
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630333"
---
# <a name="setting-the-url-property-of-the-web-service"></a><span data-ttu-id="752c8-102">Impostazione della proprietà Url del servizio Web</span><span class="sxs-lookup"><span data-stu-id="752c8-102">Setting the Url Property of the Web Service</span></span>
  <span data-ttu-id="752c8-103">In qualsiasi momento nelle [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] applicazioni è possibile modificare l'URL di base del servizio Web ReportServer a cui è attualmente diretta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="752c8-103">At any time in your [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] applications, you can modify the base URL of the Report Server Web service to which your application is currently directed.</span></span> <span data-ttu-id="752c8-104">A tale scopo, è sufficiente impostare la proprietà **Url** dell'oggetto servizio.</span><span class="sxs-lookup"><span data-stu-id="752c8-104">To do this, simply set the **Url** property of the service object.</span></span> <span data-ttu-id="752c8-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="752c8-105">For example:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx"  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx";  
```  
  
 <span data-ttu-id="752c8-106">L'esempio seguente consente di recuperare una definizione del report da un server di report e di utilizzare tale definizione per creare un report identico in un server di report diverso:</span><span class="sxs-lookup"><span data-stu-id="752c8-106">The following example retrieves a report definition from one report server and uses that definition to create an identical report on a different report server:</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
  
Class Sample  
   Public Shared Sub Main()  
      Dim rs As New ReportingService2010()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx"  
  
      Dim reportName As String = "/SampleReports/Company Sales"  
      Dim reportDefinition As Byte() = Nothing  
  
      Try  
         ' Get the report definition of a report on a source server  
         reportDefinition = rs.GetItemDefinition(reportName)  
         ' Set the base Web service URL of the destination server  
         rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx"  
         ' Create a copy of the report on the destination server  
         Dim warnings As Warning() = {}  
         rs.CreateCatalogItem("Report", "Company Sales Copy", "/", False, reportDefinition, Nothing, warnings)        
      Catch e As SoapException  
         Console.WriteLine(e.Detail.InnerXml.ToString())  
      End Try  
   End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;  
  
class Sample  
{  
   public static void Main()  
   {  
      ReportingService2010 rs = new ReportingService2010();  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/reportservice2010.asmx";  
  
      string reportName = "/SampleReports/Company Sales";  
      byte[] reportDefinition = null;  
  
      try  
      {  
         reportDefinition = rs.GetItemDefinition(reportName);  
         // Set the base Web service URL of the destination server  
         rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx";  
         // Create a copy of the report on the destination server  
         Warning[] warnings = {};  
         rs.CreateCatalogItem("Report", "Company Sales Copy", "/", false, reportDefinition, null, out warnings);  
      }  
  
      catch (SoapException e)  
      {  
         Console.WriteLine(e.Detail.InnerXml.ToString());   
      }  
   }  
}  
```  
  
 <span data-ttu-id="752c8-107">Per altre informazioni sulla creazione del proxy del servizio Web iniziale, vedere [Creazione del proxy del servizio Web](creating-the-web-service-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="752c8-107">For more information about creating the initial Web service proxy, see [Creating the Web Service Proxy](creating-the-web-service-proxy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="752c8-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="752c8-108">See Also</span></span>  
 <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A>   
 <xref:ReportService2010.ReportingService2010.GetItemDefinition%2A>   
 <span data-ttu-id="752c8-109">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="752c8-109">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="752c8-110">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="752c8-110">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
