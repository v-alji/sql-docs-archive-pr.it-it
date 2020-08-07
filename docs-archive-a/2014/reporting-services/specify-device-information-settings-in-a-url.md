---
title: Specificare le impostazioni relative alle informazioni sul dispositivo in un URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], URLs
- URL access [Reporting Services], device information settings
ms.assetid: cb7f7577-c6a8-4e6f-8e60-5ec0760f29c3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00cd1fdc3b5fbe129ae4d51b220a11bc48b4744c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719445"
---
# <a name="specify-device-information-settings-in-a-url"></a><span data-ttu-id="54bf9-102">Specificare le impostazioni relative alle informazioni sul dispositivo in un URL</span><span class="sxs-lookup"><span data-stu-id="54bf9-102">Specify Device Information Settings in a URL</span></span>
  <span data-ttu-id="54bf9-103">Le impostazioni relative alle informazioni sul dispositivo sono parametri passati a un'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="54bf9-103">Device information settings are parameters that are passed to a rendering extension.</span></span> <span data-ttu-id="54bf9-104">Se si utilizzano i metodi del servizio Web ReportServer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per eseguire il rendering di un report, come parametro di input viene passato un elemento `DeviceInfo` XML.</span><span class="sxs-lookup"><span data-stu-id="54bf9-104">If you use the methods of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service to render a report, a `DeviceInfo` XML element is passed as an input parameter.</span></span> <span data-ttu-id="54bf9-105">Gli elementi figlio dell'elemento `DeviceInfo` sono specifici delle impostazioni relative alle informazioni sul dispositivo di diverse estensioni per il rendering.</span><span class="sxs-lookup"><span data-stu-id="54bf9-105">Child elements of the `DeviceInfo` element are specific to the device information settings of different rendering extensions.</span></span> <span data-ttu-id="54bf9-106">È possibile includere le impostazioni relative alle informazioni sul dispositivo in un URL usando la stringa di parametri *rc:tag=value* , dove *tag* è il nome dell'elemento delle impostazioni relative alle informazioni sul dispositivo a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="54bf9-106">You can include device information settings in a URL by using the *rc:tag=value* parameter string, where *tag* is the name of the device information settings element being accessed.</span></span> <span data-ttu-id="54bf9-107">Per altre informazioni sulle impostazioni relative alle informazioni sul dispositivo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vedere [Passaggio delle impostazioni relative alle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="54bf9-107">For more information about device information settings in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54bf9-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="54bf9-108">Example</span></span>  
 <span data-ttu-id="54bf9-109">L'esempio seguente imposta il formato del report specificato su JPEG usando l'impostazione relativa alle informazioni sul dispositivo *OutputFormat* dell'estensione per il rendering dell'immagine. Le interruzioni di riga sono state aggiunte per migliorare la leggibilità:</span><span class="sxs-lookup"><span data-stu-id="54bf9-109">The following example sets the format of the specified report to JPEG by using the *OutputFormat* device information setting of the image rendering extension (the line breaks have been added for legibility):</span></span>  
  
```  
http://servername/reportserver?/SampleReports  
/Employee Sales Summary&EmployeeID=38&rs:  
Command=Render&rs:Format=IMAGE&rc:OutputFormat=JPEG  
```  
  
## <a name="see-also"></a><span data-ttu-id="54bf9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54bf9-110">See Also</span></span>  
 <span data-ttu-id="54bf9-111">[Accesso con URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="54bf9-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="54bf9-112">Riferimento ai parametri di accesso con URL</span><span class="sxs-lookup"><span data-stu-id="54bf9-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
