---
title: Using the IDeliveryReportServerInformation Interface for a Delivery Extension (Uso dell'interfaccia IDeliveryReportServerInformation per un'estensione per il recapito) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IDeliveryReportServerInformation interface
- delivery extensions [Reporting Services], retrieving report server information
ms.assetid: adbce647-18f3-470c-8114-42f8bcc95dc2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52e137d1a866305ec6435a4940fe98448bce5778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638286"
---
# <a name="using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension"></a><span data-ttu-id="cf886-102">Utilizzo dell'interfaccia IDeliveryReportServerInformation per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="cf886-102">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>
  <span data-ttu-id="cf886-103">L'interfaccia <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> espone diverse proprietà che è possibile utilizzare per recuperare informazioni su un server di report.</span><span class="sxs-lookup"><span data-stu-id="cf886-103">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface exposes several properties that you can use to retrieve information about a report server.</span></span> <span data-ttu-id="cf886-104">È possibile utilizzare queste informazioni per recapitare notifiche e report.</span><span class="sxs-lookup"><span data-stu-id="cf886-104">You can use this information to deliver notifications and reports.</span></span> <span data-ttu-id="cf886-105">Quando si implementa la classe di estensioni per il recapito, si implementa la proprietà <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A>, come richiesto dall'interfaccia <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="cf886-105">When implementing your delivery extension class, you implement the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property as required by the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="cf886-106">La proprietà <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> restituisce un oggetto che implementa l'interfaccia <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>.</span><span class="sxs-lookup"><span data-stu-id="cf886-106">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property returns an object that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface.</span></span> <span data-ttu-id="cf886-107">Da questo oggetto è possibile ottenere un elenco di estensioni per il rendering attualmente supportate dal server di report.</span><span class="sxs-lookup"><span data-stu-id="cf886-107">From this object you can get a list of rendering extensions currently supported by the report server.</span></span>  
  
 <span data-ttu-id="cf886-108">Il `for` ciclo seguente può essere utilizzato per archiviare un elenco di estensioni per il rendering attualmente disponibili nel server di report in un oggetto **ArrayList** .</span><span class="sxs-lookup"><span data-stu-id="cf886-108">The following `for` loop could be used to store a list of rendering extensions currently available on the report server in an **ArrayList** object.</span></span>  
  
```vb  
Dim renderFormats As New ArrayList()  
Dim e As Microsoft.ReportingServices.Interfaces.Extension  
For Each e In  ReportServerInformation.RenderingExtension  
   If e.Visible Then  
      renderFormats.Add(e.Name)  
   End If  
Next e  
```  
  
```csharp  
ArrayList renderFormats = new ArrayList();  
foreach (Microsoft.ReportingServices.Interfaces.Extension e in ReportServerInformation.RenderingExtension)  
{   
   if (e.Visible)  
   {  
      renderFormats.Add(e.Name);  
   }  
}  
```  
  
 <span data-ttu-id="cf886-109">Per altre informazioni sull'interfaccia <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>, [vedere Uso dell'interfaccia IDeliveryReportServerInformation per un'estensione per il recapito](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="cf886-109">For more information about the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface, see [Using the IDeliveryReportServerInformation Interface for a Delivery Extension](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf886-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf886-110">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="cf886-111">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="cf886-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="cf886-112">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cf886-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
