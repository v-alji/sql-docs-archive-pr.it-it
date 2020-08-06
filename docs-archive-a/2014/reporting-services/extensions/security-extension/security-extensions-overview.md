---
title: Panoramica delle estensioni di sicurezza| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9cd6c2a1518b724a7faafecdb2926505694e9707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629215"
---
# <a name="security-extensions-overview"></a><span data-ttu-id="b0aa2-102">Panoramica sulle estensioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b0aa2-102">Security Extensions Overview</span></span>
  <span data-ttu-id="b0aa2-103">Un'estensione di sicurezza di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] consente l'autenticazione e l'autorizzazione di utenti o gruppi, ovvero consente a utenti diversi di accedere a un server di report e, sulla base delle relative identità, di eseguire diverse attività o operazioni.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-103">A [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension enables the authentication and authorization of users or groups; that is, it enables different users to log on to a report server and, based on their identities, perform different tasks or operations.</span></span> <span data-ttu-id="b0aa2-104">Per impostazione predefinita, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] utilizza un'estensione di autenticazione basata su Windows che verifica le identità degli utenti che dichiarano di avere account nel sistema tramite i protocolli degli account di Windows.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-104">By default, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a Windows-based authentication extension, which uses Windows account protocols to verify the identities of users who claim to have accounts on the system.</span></span> <span data-ttu-id="b0aa2-105">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] l'autorizzazione degli utenti viene effettuata tramite un sistema di sicurezza basato sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a role-based security system to authorize users.</span></span> <span data-ttu-id="b0aa2-106">Il modello di sicurezza basato sui ruoli di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] è simile ai modelli di sicurezza basati sui ruoli di altre tecnologie.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-106">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] role-based security model is similar to the role-based security models of other technologies.</span></span>

 <span data-ttu-id="b0aa2-107">Poiché le estensioni di sicurezza si basano su un'API aperta ed estensibile, è possibile creare nuove estensioni di autenticazione e autorizzazione in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0aa2-107">Because security extensions are based on an open and extensible API, you can create new authentication and authorization extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="b0aa2-108">Di seguito viene fornito un esempio di una tipica implementazione dell'estensione di sicurezza in cui l'autenticazione e l'autorizzazione sono basate su form:</span><span class="sxs-lookup"><span data-stu-id="b0aa2-108">The following is an example of a typical security extension implementation that uses Forms-based authentication and authorization:</span></span>

 <span data-ttu-id="b0aa2-109">![Processo dell'estensione di sicurezza di Reporting Services](../../media/rosettasecurityextensionflow.gif "Processo dell'estensione di sicurezza di Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="b0aa2-109">![Reporting Services security extension process](../../media/rosettasecurityextensionflow.gif "Reporting Services security extension process")</span></span>

 <span data-ttu-id="b0aa2-110">Come illustrato nella figura, l'autenticazione e l'autorizzazione vengono effettuate nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b0aa2-110">As shown in the illustration, authentication and authorization occur as follows:</span></span>

1.  <span data-ttu-id="b0aa2-111">Un utente tenta di accedere a Gestione report mediante un URL e viene reindirizzato a un form che ne raccoglie le credenziali per l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-111">A user tries to access Report Manager by using a URL and is redirected to a form that collects user credentials for the client application.</span></span>

2.  <span data-ttu-id="b0aa2-112">L'utente invia le credenziali al form.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-112">The user submits credentials to the form.</span></span>

3.  <span data-ttu-id="b0aa2-113">Le credenziali utente vengono inviate al servizio Web Reporting Services tramite il metodo <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-113">The user credentials are submitted to the Reporting Services Web service through the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span>

4.  <span data-ttu-id="b0aa2-114">Il servizio Web chiama l'estensione di sicurezza fornita dal cliente e verifica che nome utente e password siano presenti nell'autorità di sicurezza personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-114">The Web service calls the customer-supplied security extension and verifies that the user name and password exist in the custom security authority.</span></span>

5.  <span data-ttu-id="b0aa2-115">Dopo l'autenticazione, il servizio Web crea e gestisce un ticket di autenticazione (noto come "cookie"), quindi verifica il ruolo dell'utente per la home page di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-115">After authentication, the Web service creates an authentication ticket (known as a "cookie"), manages the ticket, and verifies the user's role for the Home page of Report Manager.</span></span>

6.  <span data-ttu-id="b0aa2-116">Il servizio Web restituisce il cookie al browser e visualizza l'interfaccia utente appropriata in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-116">The Web service returns the cookie to the browser and displays the appropriate user interface in Report Manager.</span></span>

7.  <span data-ttu-id="b0aa2-117">Dopo l'autenticazione dell'utente, il browser invia richieste a Gestione report durante la trasmissione del cookie nell'intestazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-117">After the user is authenticated, the browser makes requests to Report Manager while transmitting the cookie in the HTTP header.</span></span> <span data-ttu-id="b0aa2-118">Queste richieste vengono inviate in risposta alle azioni dell'utente all'interno dell'applicazione Gestione report.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-118">These requests are in response to user actions within the Report Manager application.</span></span>

8.  <span data-ttu-id="b0aa2-119">Il cookie viene trasmesso nell'intestazione HTTP al servizio Web insieme all'operazione utente richiesta.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-119">The cookie is transmitted in the HTTP header to the Web service along with the requested user operation.</span></span>

9. <span data-ttu-id="b0aa2-120">Il cookie viene convalidato e, se valido, il server di report restituisce il descrittore di sicurezza e altre informazioni relative all'operazione richiesta dal database del server di report.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-120">The cookie is validated, and if it is valid, the report server returns the security descriptor and other information relating to the requested operation from the report server database.</span></span>

10. <span data-ttu-id="b0aa2-121">Se il cookie è valido, il server di report effettua una chiamata all'estensione di sicurezza per controllare se l'utente è autorizzato a eseguire l'operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-121">If the cookie is valid, the report server makes a call to the security extension to check if the user is authorized to perform the specific operation.</span></span>

11. <span data-ttu-id="b0aa2-122">Se l'utente è autorizzato, il server di report esegue l'operazione richiesta e restituisce il controllo al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-122">If the user is authorized, the report server performs the requested operation and returns control to the caller.</span></span>

12. <span data-ttu-id="b0aa2-123">Dopo l'autenticazione dell'utente, l'accesso all'URL per il server di report utilizza lo stesso cookie.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-123">After the user is authenticated, URL access to the report server uses the same cookie.</span></span> <span data-ttu-id="b0aa2-124">Il cookie viene trasmesso nell'intestazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-124">The cookie is transmitted in the HTTP header.</span></span>

13. <span data-ttu-id="b0aa2-125">L'utente continua a richiedere operazioni sul server di report fino al termine della sessione.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-125">The user continues to request operations on the report server until the session has ended.</span></span>

## <a name="when-to-implement-a-security-extension"></a><span data-ttu-id="b0aa2-126">Quando implementare un'estensione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b0aa2-126">When to Implement a Security Extension</span></span>
 <span data-ttu-id="b0aa2-127">Se possibile, si consiglia di utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-127">We recommend that you use Windows Authentication if at all possible.</span></span> <span data-ttu-id="b0aa2-128">Tuttavia, l'autenticazione e l'autorizzazione personalizzate per [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] possono essere appropriate nei due casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0aa2-128">However, custom authentication and authorization for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] may be appropriate in the following two cases:</span></span>

-   <span data-ttu-id="b0aa2-129">Si dispone di un'applicazione Internet o Extranet in cui non è possibile utilizzare gli account di Windows.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-129">You have an Internet or extranet application that cannot use Windows accounts.</span></span>

-   <span data-ttu-id="b0aa2-130">Si dispone di utenti e ruoli personalizzati ed è necessario fornire uno schema di autorizzazione corrispondente in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0aa2-130">You have custom-defined users and roles and need to provide a matching authorization scheme in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="b0aa2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0aa2-131">See Also</span></span>
 <span data-ttu-id="b0aa2-132">[Implementazione di un'estensione](../security-extension/implementing-a-security-extension.md) [di sicurezza configurare Gestione report per il passaggio di cookie di autenticazione personalizzati](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span><span class="sxs-lookup"><span data-stu-id="b0aa2-132">[Implementing a Security Extension](../security-extension/implementing-a-security-extension.md) [Configure Report Manager to Pass Custom Authentication Cookies](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span></span>


