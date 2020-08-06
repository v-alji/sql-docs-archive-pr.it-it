---
title: Autenticazione del servizio Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], authentication
- XML Web service [Reporting Services], authentication
- Report Server Web service, authentication
ms.assetid: 852b4947-a090-4e54-8555-5a503945ceab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0c7836d6eba8c6ab3f0a8e705ebb79c7ed73eb17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723364"
---
# <a name="web-service-authentication"></a><span data-ttu-id="1347a-102">Autenticazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="1347a-102">Web Service Authentication</span></span>
  <span data-ttu-id="1347a-103">Per autenticare le chiamate effettuate al servizio Web ReportServer, è possibile utilizzare l'autenticazione di Windows o l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="1347a-103">You can use either Windows Authentication or Basic authentication to authenticate the calls made to the Report Server Web service.</span></span> <span data-ttu-id="1347a-104">Qualsiasi client che effettua richieste SOAP al server di report deve implementare la parte client di uno dei protocolli di autenticazione supportati.</span><span class="sxs-lookup"><span data-stu-id="1347a-104">Any client that makes SOAP requests to the report server must implement the client portion of one of the supported authentication protocols.</span></span> <span data-ttu-id="1347a-105">Se si utilizza [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , è possibile utilizzare le classi http di codice gestito per implementare l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1347a-105">If you are using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], you can use the managed code HTTP classes to implement authentication.</span></span> <span data-ttu-id="1347a-106">L'utilizzo di queste API semplifica l'invio delle informazioni di autenticazione insieme alle richieste SOAP.</span><span class="sxs-lookup"><span data-stu-id="1347a-106">Using these APIs makes it easy to send authentication information along with the SOAP requests.</span></span>  
  
 <span data-ttu-id="1347a-107">Se non si dispone delle credenziali appropriate prima di effettuare una chiamata al servizio Web ReportServer, la chiamata ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1347a-107">If you do not have appropriate credentials before you make a call to the Report Server Web service, the call fails.</span></span> <span data-ttu-id="1347a-108">In fase di esecuzione è possibile passare le credenziali al servizio Web impostando la proprietà **Credenziali** dell'oggetto sul lato client che rappresenta il servizio Web prima di chiamarne i metodi.</span><span class="sxs-lookup"><span data-stu-id="1347a-108">At run time, you can pass credentials to the Web service by setting the **Credentials** property of the client-side object that represents the Web service before you call its methods.</span></span>  
  
 <span data-ttu-id="1347a-109">Nelle sezioni seguenti sono inclusi esempi di codice per l'invio delle credenziali utilizzando [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1347a-109">The following sections contain example code that sends credentials using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="1347a-110">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="1347a-110">Windows Authentication</span></span>  
 <span data-ttu-id="1347a-111">Nel codice seguente vengono passate le credenziali di Windows al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="1347a-111">The following code passes Windows credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
ReportingService rs = new ReportingService();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
```  
  
## <a name="basic-authentication"></a><span data-ttu-id="1347a-112">Autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="1347a-112">Basic Authentication</span></span>  
 <span data-ttu-id="1347a-113">Nel codice seguente vengono passate le credenziali di base al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="1347a-113">The following code passes Basic credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = New System.Net.NetworkCredential("username", "password", "domain")  
```  
  
```csharp  
ReportingService service = new ReportingService();  
service.Credentials = new System.Net.NetworkCredential("username", "password", "domain");  
```  
  
 <span data-ttu-id="1347a-114">Le credenziali devono essere impostate prima di chiamare i metodi del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="1347a-114">The credentials must be set before you call any of the methods of the Report Server Web service.</span></span> <span data-ttu-id="1347a-115">Se non si impostano le credenziali, viene visualizzato il codice di errore Errore HTTP 401: Accesso negato.</span><span class="sxs-lookup"><span data-stu-id="1347a-115">If you do not set the credentials, you receive the error code an HTTP 401 Error: Access Denied.</span></span> <span data-ttu-id="1347a-116">È necessario autenticare il servizio prima di utilizzarlo, ma dopo avere impostato le credenziali non è necessario impostarle di nuovo fino a quando si continua a utilizzare la stessa variabile del servizio (ad esempio *rs*).</span><span class="sxs-lookup"><span data-stu-id="1347a-116">You must authenticate the service before you use it, but after you have set the credentials, you do not need to set them again as long as you continue to use the same service variable (such as *rs*).</span></span>  
  
## <a name="custom-authentication"></a><span data-ttu-id="1347a-117">Autenticazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="1347a-117">Custom Authentication</span></span>  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1347a-118">include un'API di programmazione che consente agli sviluppatori di progettare e sviluppare estensioni di autenticazione personalizzate, note come estensioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1347a-118">includes a programming API that provides developers with the opportunity to design and develop custom authentication extensions, known as security extensions.</span></span> <span data-ttu-id="1347a-119">Per ulteriori informazioni, vedere [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="1347a-119">For more information, see [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1347a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1347a-120">See Also</span></span>  
 <span data-ttu-id="1347a-121">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="1347a-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="1347a-122">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="1347a-122">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
