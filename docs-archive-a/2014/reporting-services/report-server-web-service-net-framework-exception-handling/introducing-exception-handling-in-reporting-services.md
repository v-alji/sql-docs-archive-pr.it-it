---
title: Introduzione alla gestione delle eccezioni in Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 091b1f40d293515617e369b750a5f18dfe12951b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715100"
---
# <a name="introducing-exception-handling-in-reporting-services"></a><span data-ttu-id="398b2-102">Introduzione alla gestione delle eccezioni in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="398b2-102">Introducing Exception Handling in Reporting Services</span></span>
  <span data-ttu-id="398b2-103">Se l'applicazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] invia al servizio Web ReportServer una richiesta che non può essere elaborata, viene restituita al client un'eccezione SOAP.</span><span class="sxs-lookup"><span data-stu-id="398b2-103">If your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] application sends a request to the Report Server Web service that the service is unable to process, the service returns a SOAP exception to the client.</span></span> <span data-ttu-id="398b2-104">La gestione delle eccezioni generate dal servizio Web ReportServer costituisce una parte importante dello sviluppo delle applicazioni, in quanto quando si verificano gli errori è possibile restituire agli utenti informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="398b2-104">Handling exceptions thrown by the Report Server Web service is an important part of the applications that you develop because you can return useful information to users when errors occur.</span></span>  
  
 <span data-ttu-id="398b2-105">In questa sezione sono incluse informazioni specifiche sulla gestione delle eccezioni, su come impedire agli utenti di immettere input non valido e su come restituire agli utenti informazioni significative sugli errori.</span><span class="sxs-lookup"><span data-stu-id="398b2-105">This section contains specific information about handling exceptions, preventing user input that is not valid, and returning meaningful error information to users.</span></span> <span data-ttu-id="398b2-106">Per informazioni generali sulla gestione delle eccezioni, vedere "gestione e generazione di eccezioni" nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentazione di SDK.</span><span class="sxs-lookup"><span data-stu-id="398b2-106">For general information about exception handling, see "Handling and Throwing Exceptions" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="398b2-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="398b2-107">In This Section</span></span>  
  
|<span data-ttu-id="398b2-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="398b2-108">Topic</span></span>|<span data-ttu-id="398b2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="398b2-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="398b2-110">Gestione delle eccezioni in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="398b2-110">Handling Exceptions in Reporting Services</span></span>](handling-exceptions-in-reporting-services.md)|<span data-ttu-id="398b2-111">Viene fornita una panoramica delle eccezioni in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e del ruolo di SOAP nel restituire errori da un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="398b2-111">Provides an overview of exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and the role of SOAP in returning errors from a Web service.</span></span>|  
|[<span data-ttu-id="398b2-112">Procedure consigliate per la gestione delle eccezioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="398b2-112">Best Practices for Reporting Services Exception Handling</span></span>](best-practices/best-practices-for-reporting-services-exception-handling.md)|<span data-ttu-id="398b2-113">Vengono forniti consigli sulla gestione delle eccezioni in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="398b2-113">Provides recommendations on how to handle exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="398b2-114">Classe SoapException di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="398b2-114">Reporting Services SoapException Class</span></span>](soapexception-class/reporting-services-soapexception-class.md)|<span data-ttu-id="398b2-115">Descrive la classe **SoapException** in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="398b2-115">Describes the **SoapException** class in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="398b2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="398b2-116">See Also</span></span>  
 [<span data-ttu-id="398b2-117">Compilazione di applicazioni tramite servizio Web e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="398b2-117">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
