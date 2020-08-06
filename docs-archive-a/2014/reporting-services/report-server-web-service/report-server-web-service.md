---
title: Servizio Web ReportServer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SSIS, Web service
- Web service [Reporting Services]
- Reporting Services, extending
- SQL Server Reporting Services, Web service
- Reporting Services, Web service
- XML Web service [Reporting Services]
- Report Server Web service
ms.assetid: 16c21dec-6b46-4497-9a0c-1b0f2b6ab8fc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8bb43a0fa52a243bd250f70fac16e18d949f8197
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628349"
---
# <a name="report-server-web-service"></a><span data-ttu-id="ddc99-102">servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="ddc99-102">Report Server Web Service</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="ddc99-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]consente di accedere alle funzionalità complete del server di report tramite il servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="ddc99-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] provides access to the full functionality of the report server through the Report Server Web service.</span></span> <span data-ttu-id="ddc99-104">Il servizio Web ReportServer è un servizio Web XML con un'API SOAP.</span><span class="sxs-lookup"><span data-stu-id="ddc99-104">The Report Server Web service is an XML Web service with a SOAP API.</span></span> <span data-ttu-id="ddc99-105">Il servizio usano SOAP su HTTP e funge da interfaccia di comunicazione tra i programmi client e il server di report.</span><span class="sxs-lookup"><span data-stu-id="ddc99-105">It uses SOAP over HTTP and acts as a communications interface between client programs and the report server.</span></span> <span data-ttu-id="ddc99-106">Il servizio Web fornisce due endpoint, uno per l'esecuzione dei report e uno per la gestione dei report, con metodi che espongono le funzionalità del server di report e consentono di creare strumenti personalizzati per qualsiasi parte del ciclo di vita del report.</span><span class="sxs-lookup"><span data-stu-id="ddc99-106">The Web service provides two endpoints - one for report execution and one for report management - with methods that expose the functionality of the report server and enable you to create custom tools for any part of the report life cycle.</span></span>  
  
 <span data-ttu-id="ddc99-107">Sono disponibili tre modi per sviluppare applicazioni [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] basate sul servizio Web.</span><span class="sxs-lookup"><span data-stu-id="ddc99-107">There are three primary ways to develop [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications based on the Web service.</span></span> <span data-ttu-id="ddc99-108">È possibile:</span><span class="sxs-lookup"><span data-stu-id="ddc99-108">You can:</span></span>  
  
-   <span data-ttu-id="ddc99-109">Sviluppare applicazioni usando [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] e l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="ddc99-109">Develop applications using [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span> <span data-ttu-id="ddc99-110">Per altre informazioni sull'uso di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] per la compilazione di applicazioni del servizio Web, vedere [Compilazione di applicazioni tramite servizio Web e .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="ddc99-110">For more information about using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] to build Web service applications, see [Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span></span>  
  
-   <span data-ttu-id="ddc99-111">Sviluppare applicazioni usando l'utilità **rs** (RS.exe), l'ambiente di script [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddc99-111">Develop applications using the **rs** utility (RS.exe), the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script environment.</span></span> <span data-ttu-id="ddc99-112">Gli script di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] consentono di eseguire qualsiasi operazione del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="ddc99-112">With [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] scripts, you can run any of the Report Server Web service operations.</span></span> <span data-ttu-id="ddc99-113">Per altre informazioni sull'esecuzione di script in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vedere [Eseguire lo script con l'utilità rs.exe e il servizio Web](../tools/script-with-the-rs-exe-utility-and-the-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="ddc99-113">For more information about scripting in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], see [Script with the rs.exe Utility and the Web Service](../tools/script-with-the-rs-exe-utility-and-the-web-service.md).</span></span>  
  
-   <span data-ttu-id="ddc99-114">Sviluppare applicazioni usando qualsiasi set di strumenti di sviluppo abilitato per SOAP.</span><span class="sxs-lookup"><span data-stu-id="ddc99-114">Develop applications using any SOAP-enabled set of development tools.</span></span> <span data-ttu-id="ddc99-115">Per altre informazioni, vedere [Ruolo di SOAP in Reporting Services](../report-server-web-service/the-role-of-soap-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ddc99-115">For more information, see [The Role of SOAP in Reporting Services](../report-server-web-service/the-role-of-soap-in-reporting-services.md).</span></span>  
  
## <a name="programming-diagram"></a><span data-ttu-id="ddc99-116">Diagramma di programmazione</span><span class="sxs-lookup"><span data-stu-id="ddc99-116">Programming Diagram</span></span>  
 <span data-ttu-id="ddc99-117">![Opzioni di sviluppo del servizio Web ReportServer](../../../2014/reporting-services/media/reportserviceswebserviceprog-01.gif "Opzioni di sviluppo del servizio Web ReportServer")</span><span class="sxs-lookup"><span data-stu-id="ddc99-117">![Report Server Web service development options](../../../2014/reporting-services/media/reportserviceswebserviceprog-01.gif "Report Server Web service development options")</span></span>  
<span data-ttu-id="ddc99-118">Opzioni di sviluppo dei servizi Web disponibili in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ddc99-118">Reporting Services available Web service development options</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddc99-119">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ddc99-119">In This Section</span></span>  
 [<span data-ttu-id="ddc99-120">Metodi del servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="ddc99-120">Report Server Web Service Methods</span></span>](../report-server-web-service/methods/report-server-web-service-methods.md)  
 <span data-ttu-id="ddc99-121">Vengono descritti i metodi e le caratteristiche di ogni servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="ddc99-121">Describes the features and methods of each Report Server Web service.</span></span>  
  
 [<span data-ttu-id="ddc99-122">Ruolo di SOAP in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ddc99-122">The Role of SOAP in Reporting Services</span></span>](../report-server-web-service/the-role-of-soap-in-reporting-services.md)  
 <span data-ttu-id="ddc99-123">Viene fornita una panoramica su SOAP e sul suo utilizzo nei servizi Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="ddc99-123">Provides an overview of SOAP and how it is used in the Report Server Web services.</span></span>  
  
 [<span data-ttu-id="ddc99-124">Accesso all'API SOAP</span><span class="sxs-lookup"><span data-stu-id="ddc99-124">Accessing the SOAP API</span></span>](../report-server-web-service/accessing-the-soap-api.md)  
 <span data-ttu-id="ddc99-125">Viene descritto il linguaggio WSDL (Web Service Description Language) e vengono forniti gli URL per l'accesso a un file WSDL di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ddc99-125">Describes the Web Service Description Language (WSDL) and provides URLs for accessing a Reporting Services WSDL file.</span></span>  
  
 [<span data-ttu-id="ddc99-126">Compilazione di applicazioni tramite servizio Web e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ddc99-126">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
 <span data-ttu-id="ddc99-127">Sono incluse informazioni sullo sviluppo di applicazioni e servizi Web che chiamano l'API SOAP di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ddc99-127">Contains information about developing applications and Web services that call the Reporting Services SOAP API.</span></span>  
  
 [<span data-ttu-id="ddc99-128">Eseguire lo script con l'utilità rs.exe e il servizio Web</span><span class="sxs-lookup"><span data-stu-id="ddc99-128">Script with the rs.exe Utility and the Web Service</span></span>](../tools/script-with-the-rs-exe-utility-and-the-web-service.md)  
 <span data-ttu-id="ddc99-129">Viene fornita una panoramica sull'ambiente di scripting [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddc99-129">Provides an overview of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scripting environment.</span></span>  
  
 [<span data-ttu-id="ddc99-130">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ddc99-130">Technical Reference &#40;SSRS&#41;</span></span>](../../../2014/reporting-services/technical-reference-ssrs.md)  
 <span data-ttu-id="ddc99-131">È incluso materiale di riferimento specifico dei metodi dei servizi Web ReportServer e dei tipi complessi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ddc99-131">Contains reference material specific to Report Server Web services methods and corresponding complex types.</span></span>  
  
## <a name="user-requirements-for-web-service-development"></a><span data-ttu-id="ddc99-132">Requisiti utente per lo sviluppo del servizio Web</span><span class="sxs-lookup"><span data-stu-id="ddc99-132">User Requirements for Web Service Development</span></span>  
 <span data-ttu-id="ddc99-133">Per sviluppare applicazioni usando il servizio Web ReportServer, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ddc99-133">To develop applications using the Report Server Web service, you need:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ddc99-134">Internet Explorer 5.5 o versione successiva installato in un computer con una connessione Internet e accesso al server di report.</span><span class="sxs-lookup"><span data-stu-id="ddc99-134">Internet Explorer 5.5 or later installed on a computer with an Internet connection to and access to the report server.</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="ddc99-135">[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]o il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK installato in un computer se si desidera sviluppare e distribuire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applicazioni utilizzando [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddc99-135">[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK installed on a computer if you want to develop and deploy [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span>  
  
-   <span data-ttu-id="ddc99-136">Conoscenza approfondita delle caratteristiche e delle funzionalità di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddc99-136">An in-depth understanding of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features and capabilities.</span></span>  
  
-   <span data-ttu-id="ddc99-137">Buona conoscenza di SOAP e [!INCLUDE[vstecwebservices](../../includes/vstecwebservices-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddc99-137">A firm understanding of SOAP and [!INCLUDE[vstecwebservices](../../includes/vstecwebservices-md.md)].</span></span>  
  
-   <span data-ttu-id="ddc99-138">Esperienza di sviluppo in un [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] linguaggio compatibile con, ad esempio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] , se si prevede di usare [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] come piattaforma di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ddc99-138">Development experience in a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-compatible language such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], if you plan to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] as your development platform.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc99-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddc99-139">See Also</span></span>  
 [<span data-ttu-id="ddc99-140">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="ddc99-140">Report Server Web Service</span></span>](../report-server-web-service/report-server-web-service.md)  
  
  
