---
title: Integrazione di Reporting Services tramite l'accesso con URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- URL access [Reporting Services], about URL access
- integrating reports [Reporting Services]
ms.assetid: f1014f7d-fafa-4aa8-8bd2-5bdba835d9b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fedf4ce3011d9caae9d673acf354265537115057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719722"
---
# <a name="integrating-reporting-services-using-url-access"></a><span data-ttu-id="bd0dc-102">Integrazione di Reporting Services tramite l'accesso con URL</span><span class="sxs-lookup"><span data-stu-id="bd0dc-102">Integrating Reporting Services Using URL Access</span></span>
  <span data-ttu-id="bd0dc-103">L'accesso con URL consente di accedere ai report tramite un URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-103">With URL access, you access reports through a report server URL.</span></span> <span data-ttu-id="bd0dc-104">Una richiesta URL consente di accedere a un server di report specifico, nonché ai report, alle risorse e agli altri elementi presenti nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-104">A URL request enables you to access a specific report server as well as the reports, resources, and other items in the report server database.</span></span> <span data-ttu-id="bd0dc-105">È anche possibile personalizzare la visualizzazione del report e l'esperienza di navigazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-105">You can also customize the report viewing and navigation experience for your users.</span></span> <span data-ttu-id="bd0dc-106">La stringa di query dell'URL contiene le impostazioni relative alle informazioni sul dispositivo, nonché i parametri del report e l'output di rendering scelto.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-106">The query string of the URL contains device information settings, as well as report parameters targeted at your report and the chosen rendering output.</span></span> <span data-ttu-id="bd0dc-107">Il modo in cui le richieste URL vengono gestite dal server di report dipende dai parametri, dai prefissi di parametro e dal tipo di elemento a cui si accede tramite l'URL.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-107">The way the report server handles URL requests depends on the parameters, parameter prefixes, and type of item that you are accessing through the URL.</span></span>  
  
 <span data-ttu-id="bd0dc-108">È possibile utilizzare l'accesso con URL per incorporare i collegamenti ipertestuali ai report e ad altri elementi del server di report nelle applicazioni sviluppate, sia in ambiente Windows che Web.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-108">You can use URL access to embed hyperlinks to reports and other report server items in the applications that you develop, whether in a Windows or Web environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd0dc-109">Negli argomenti di questa sezione vengono fornite alcune informazioni di base per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-109">The topics in the section provide you with some basic ideas for integration.</span></span> <span data-ttu-id="bd0dc-110">È possibile utilizzare le informazioni per iniziare a progettare e sviluppare scenari di integrazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd0dc-110">You can use the information to begin to design and develop your own [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integration scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd0dc-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bd0dc-111">In This Section</span></span>  
 [<span data-ttu-id="bd0dc-112">Uso dell'accesso con URL in un'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="bd0dc-112">Using URL Access in a Web Application</span></span>](integrating-reporting-services-using-url-access-web-application.md)  
 <span data-ttu-id="bd0dc-113">Viene descritto come utilizzare l'accesso con URL per integrare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un ambiente Web.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-113">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
 [<span data-ttu-id="bd0dc-114">Uso dell'accesso con URL in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="bd0dc-114">Using URL Access in a Windows Application</span></span>](integrating-reporting-services-using-url-access-windows-application.md)  
 <span data-ttu-id="bd0dc-115">Viene descritto come utilizzare l'accesso con URL per integrare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un ambiente [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32.</span><span class="sxs-lookup"><span data-stu-id="bd0dc-115">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0dc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd0dc-116">See Also</span></span>  
 <span data-ttu-id="bd0dc-117">[Integrazione di Reporting Services in applicazioni](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="bd0dc-117">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="bd0dc-118">Accesso con URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bd0dc-118">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
