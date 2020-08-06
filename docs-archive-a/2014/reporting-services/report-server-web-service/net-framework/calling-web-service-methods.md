---
title: Chiamata di metodi del servizio Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 87f1485b4e3c0ed064e42bb3b411fece96eba8d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713823"
---
# <a name="calling-web-service-methods"></a><span data-ttu-id="3d52d-102">Chiamata ai metodi del servizio Web</span><span class="sxs-lookup"><span data-stu-id="3d52d-102">Calling Web Service Methods</span></span>
  <span data-ttu-id="3d52d-103">Quando si usa una [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] classe proxy per chiamare le operazioni del servizio Web, è possibile usare i metodi di tale classe.</span><span class="sxs-lookup"><span data-stu-id="3d52d-103">When you use a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class to call Web service operations, you do so by using the methods of that class.</span></span> <span data-ttu-id="3d52d-104">Questi metodi funzionano come qualsiasi altro metodo di una classe nella libreria di classi [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d52d-104">These methods respond like any other method of a class in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="3d52d-105">Tutti i metodi del servizio Web dispongono di accesso pubblico e richiedono di fornire il numero appropriato di argomenti e tipi di argomento.</span><span class="sxs-lookup"><span data-stu-id="3d52d-105">All Web service methods have public access and require you to supply the appropriate number of arguments and argument types.</span></span> <span data-ttu-id="3d52d-106">Dopo aver creato un'istanza della classe proxy nel progetto, è possibile chiamare i metodi per eseguire operazioni relative ai report tramite il server di report.</span><span class="sxs-lookup"><span data-stu-id="3d52d-106">After you have created an instance of the proxy class in your project, you can call the methods to perform reporting operations via the report server.</span></span> <span data-ttu-id="3d52d-107">Il codice C# seguente illustra l'uso del metodo <xref:ReportService2010.ReportingService2010.ListChildren%2A> della classe proxy <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="3d52d-107">The following C# code illustrates the use of the <xref:ReportService2010.ReportingService2010.ListChildren%2A> method of the <xref:ReportService2010.ReportingService2010> proxy class.</span></span> <span data-ttu-id="3d52d-108">Il codice viene utilizzato per effettuare una chiamata ricorsiva al servizio Web che restituisce una matrice di oggetti <xref:ReportService2010.CatalogItem> contenente un elenco di tutti gli elementi nel database del server di report:</span><span class="sxs-lookup"><span data-stu-id="3d52d-108">The code is used to make a recursive call to the Web service that returns an array of <xref:ReportService2010.CatalogItem> objects that contains a list of all items in the report server database:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d52d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d52d-109">See Also</span></span>  
 <span data-ttu-id="3d52d-110">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="3d52d-110">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="3d52d-111">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="3d52d-111">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="3d52d-112">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3d52d-112">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
