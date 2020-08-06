---
title: Accesso all'API SOAP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- XML Web service [Reporting Services], WSDL
- Web service [Reporting Services], SOAP
- calling Web service
- SOAP [Reporting Services], accessing
- Report Server Web service, SOAP
- Web service [Reporting Services], WSDL
- WSDL [Reporting Services]
- XML Web service [Reporting Services], SOAP
- Report Server Web service, WSDL
- referencing WSDL
ms.assetid: 63bb870a-4dbf-46bd-8921-78f8ebe5fd75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e8a0c21bb53deff746cfd916b6ae2c96fa0de19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636544"
---
# <a name="accessing-the-soap-api"></a><span data-ttu-id="57b2d-102">Accesso all'API SOAP</span><span class="sxs-lookup"><span data-stu-id="57b2d-102">Accessing the SOAP API</span></span>
  <span data-ttu-id="57b2d-103">Il servizio Web ReportServer utilizza SOAP (Simple Object Access Protocol) tramite HTTP e funge da interfaccia di comunicazione tra i programmi client e il server di report.</span><span class="sxs-lookup"><span data-stu-id="57b2d-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) over HTTP and acts as a communications interface between client programs and the report server.</span></span> <span data-ttu-id="57b2d-104">Il servizio Web fornisce due endpoint, uno per l'esecuzione dei report e uno per la gestione dei report ed è costituito da metodi e un set di oggetti di tipo complesso che è possibile utilizzare per accedere alle funzionalità complete di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57b2d-104">The Web service provides two endpoints - one for report execution and one for report management - and consists of methods and a set of complex type objects that you can use to access the complete functionality of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="57b2d-105">Per chiamare il servizio, è necessario fare riferimento al linguaggio WSDL (Web Services Description Language) di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="57b2d-105">To call the service, you must reference the Reporting Services Web Services Description Language (WSDL).</span></span>  
  
## <a name="referencing-the-reporting-services-wsdl"></a><span data-ttu-id="57b2d-106">Riferimento al linguaggio WSDL di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="57b2d-106">Referencing the Reporting Services WSDL</span></span>  
 <span data-ttu-id="57b2d-107">Per chiamare correttamente un servizio Web, è necessario sapere come accedere al servizio, quali operazioni sono supportate dal servizio, quali parametri sono previsti dal servizio e cosa viene restituito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="57b2d-107">To call a Web service successfully, you must know how to access the service, what operations the service supports, what parameters the service expects, and what the service returns.</span></span> <span data-ttu-id="57b2d-108">WSDL fornisce queste informazioni in un documento XML che può essere letto o elaborato da un computer.</span><span class="sxs-lookup"><span data-stu-id="57b2d-108">WSDL provides this information in an XML document that can be read or processed by a computer.</span></span>  
  
 <span data-ttu-id="57b2d-109">I servizi Web ReportServer sono esposti in tre endpoint diversi.</span><span class="sxs-lookup"><span data-stu-id="57b2d-109">The Report Server Web services are exposed in three different endpoints.</span></span> <span data-ttu-id="57b2d-110">Il nome del file WSDL è diverso per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="57b2d-110">The name of the WSDL file is different for each endpoint.</span></span> <span data-ttu-id="57b2d-111">L'endpoint <xref:ReportService2010> contiene metodi per la gestione di oggetti in un server di report in modalità nativa o in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="57b2d-111">The <xref:ReportService2010> endpoint contains methods for managing objects in a Report Server in either native or SharePoint integrated mode.</span></span> <span data-ttu-id="57b2d-112">È possibile accedere al linguaggio WSDL per questo endpoint tramite `ReportService2010.asmx?wsdl.`</span><span class="sxs-lookup"><span data-stu-id="57b2d-112">The WSDL for this endpoint is accessed through `ReportService2010.asmx?wsdl.`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57b2d-113">Gli endpoint <xref:ReportService2005> e <xref:ReportService2006> sono deprecati in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57b2d-113">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="57b2d-114">L'endpoint <xref:ReportService2010> include le funzionalità di entrambi gli endpoint e contiene caratteristiche di gestione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="57b2d-114">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
-   <span data-ttu-id="57b2d-115">L'endpoint <xref:ReportExecution2005> consente agli sviluppatori di elaborare a livello di programmazione i report e di eseguirne il rendering in un server di report.</span><span class="sxs-lookup"><span data-stu-id="57b2d-115">The <xref:ReportExecution2005> endpoint allows developers to programmatically process and render reports in a Report Server.</span></span> <span data-ttu-id="57b2d-116">È possibile accedere al linguaggio WSDL per questo endpoint tramite `ReportExecution2005.asmx?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="57b2d-116">The WSDL for this endpoint is accessed through `ReportExecution2005.asmx?wsdl`.</span></span>  
  
 <span data-ttu-id="57b2d-117">WSDL può essere utilizzato dai kit di sviluppo che supportano SOAP e i servizi Web, ad esempio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="57b2d-117">WSDL can be consumed by development kits that support SOAP and Web services, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="57b2d-118">Nell'esempio seguente viene illustrato il formato dell'URL del file WSDL di gestione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="57b2d-118">The following example shows the format of the URL to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] management WSDL file:</span></span>  
  
```  
http://server/reportserver/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="57b2d-119">Nella tabella seguente sono descritti gli elementi dell'URL.</span><span class="sxs-lookup"><span data-stu-id="57b2d-119">The following table describes each element in the URL.</span></span>  
  
|<span data-ttu-id="57b2d-120">Elemento URL</span><span class="sxs-lookup"><span data-stu-id="57b2d-120">URL element</span></span>|<span data-ttu-id="57b2d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57b2d-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="57b2d-122">*server*</span><span class="sxs-lookup"><span data-stu-id="57b2d-122">*server*</span></span>|<span data-ttu-id="57b2d-123">Nome del server in cui viene distribuito il server di report.</span><span class="sxs-lookup"><span data-stu-id="57b2d-123">The name of the server on which the report server is deployed.</span></span>|  
|<span data-ttu-id="57b2d-124">*ReportServer*</span><span class="sxs-lookup"><span data-stu-id="57b2d-124">*reportserver*</span></span>|<span data-ttu-id="57b2d-125">Nome della cartella contenente il servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="57b2d-125">The name of the folder that contains the XML Web service.</span></span> <span data-ttu-id="57b2d-126">Questo nome viene configurato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="57b2d-126">This is configured during setup.</span></span>|  
|<span data-ttu-id="57b2d-127">*\<endpoint name>. asmx*</span><span class="sxs-lookup"><span data-stu-id="57b2d-127">*\<endpoint name>.asmx*</span></span>|<span data-ttu-id="57b2d-128">Nome dell'endpoint del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="57b2d-128">The name of the web service endpoint.</span></span>|  
  
 <span data-ttu-id="57b2d-129">Per altre informazioni sul formato WSDL, vedere la specifica WSDL nel sito Web World Wide Web Consortium (W3C) all'indirizzo http://www.w3.org/TR/wsdl.</span><span class="sxs-lookup"><span data-stu-id="57b2d-129">For more information about the WSDL format, see the World Wide Web Consortium (W3C) WSDL specification at http://www.w3.org/TR/wsdl.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b2d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57b2d-130">See Also</span></span>  
 <span data-ttu-id="57b2d-131">[Compilazione di applicazioni tramite servizio Web e .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="57b2d-131">[Building Applications Using the Web Service and the .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="57b2d-132">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="57b2d-132">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
